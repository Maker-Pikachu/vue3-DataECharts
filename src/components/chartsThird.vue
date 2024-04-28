<template>
    <div class="main">

        <div class="left">地图</div>
        <div class="right" ref="chart" style="width: 100%;height:100%;"></div>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
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
        legend: {
            orient: 'vertical',
            right: 10,
            top: 'center',
            textStyle:{
                color:'#fff'
            }
        },
        toolbox: {
            show: true,
            feature: {
                dataView: { show: true, readOnly: false },
                restore: { show: true },
                saveAsImage: { show: true }
            }
        },
        series: [
            {
                name: 'Nightingale Chart',
                type: 'pie',
                radius: [20, 100],
                roseType: 'area',
                center: ['50%', '50%'],
                itemStyle: {
                    borderRadius: 8
                },
                data: [
                    { value: 40, name: '交通事故' },
                    { value: 38, name: '除雪' },
                    { value: 32, name: '路基' },
                    { value: 30, name: '日常养护' },
                    { value: 28, name: '绿化' },
                    { value: 26, name: '路面' },
                    { value: 22, name: '桥通' },
                    { value: 18, name: '交安设施' }
                ],
                label:{
                    show:true,
                    formatter:'{b} {c}%',
                    color:'#fff'
                }
            }
        ]
    };
    // 绘制图表
    myChart.setOption(option);
}
</script>

<style scoped>
.main {
    display: flex;
}

.left {
    flex: 0 1 50%
}

.right {
    background: #093060;
    flex: 0 1 50%
}
</style>