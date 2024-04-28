<template>
    <div class="main">
        <div class="chart" ref="chart" style="width: 100%;height:100%;"></div>
        <Decoration2 :reverse="true" style="width:5px; height:100%;"  />
    </div>

</template>

<script setup lang="ts">
import { onMounted, ref, reactive } from 'vue'
import { Decoration2 } from '@dataview/datav-vue3';
import * as echarts from 'echarts';
const chart = ref()
// 基于准备好的dom，初始化echarts实例
onMounted(() => {
    console.log(chart.value);
    charInit()
})
function charInit() {
    var myChart = echarts.init(chart.value);
    const option = {
        series: [
            {
                type: 'gauge',
                startAngle: 180,
                endAngle: 0,
                center: ['50%', '75%'],
                radius: '90%',
                min: 0,
                max: 1,
                splitNumber: 8,
                axisLine: {
                    lineStyle: {
                        width: 6,
                        color: [
                            [0.25, '#FF6E76'],
                            [0.5, '#FDDD60'],
                            [0.75, '#58D9F9'],
                            [1, '#7CFFB2']
                        ]
                    }
                },
                pointer: {
                    icon: 'path://M12.8,0.7l12,40.1H0.7L12.8,0.7z',
                    length: '12%',
                    width: 20,
                    offsetCenter: [0, '-60%'],
                    itemStyle: {
                        color: 'auto'
                    }
                },
                axisTick: {
                    length: 12,
                    lineStyle: {
                        color: 'auto',
                        width: 2
                    }
                },
                splitLine: {
                    length: 20,
                    lineStyle: {
                        color: 'auto',
                        width: 5
                    }
                },
                axisLabel: {
                    color: '#fff',
                    fontSize: 10,
                    distance: -40,
                    rotate: 'tangential',
                    formatter: function (value: any) {
                        if (value === 0.875) {
                            return 'Grade A';
                        } else if (value === 0.625) {
                            return 'Grade B';
                        } else if (value === 0.375) {
                            return 'Grade C';
                        } else if (value === 0.125) {
                            return 'Grade D';
                        }
                        return '';
                    }
                },
                title: {
                    offsetCenter: [0, '5%'],
                    fontSize: 10,
                    color: '#fff'
                },
                detail: {
                    fontSize: 20,
                    offsetCenter: [0, '-15%'],
                    valueAnimation: true,
                    formatter: function (value: any) {
                        return Math.round(value * 100) + '';
                    },
                    color: 'inherit'
                },
                data: [
                    {
                        value: 0.6,
                        name: 'Grade Rating'
                    }
                ]
            }
        ]
    }
    // 绘制图表
    myChart.setOption(option);
}

</script>

<style scoped>
.main{
    background: #093060;
    display: flex   ;
}

</style>