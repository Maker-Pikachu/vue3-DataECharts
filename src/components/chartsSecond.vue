<template>
    <div class="mian">
        <div class="chart" ref="chart" style="width: 100%;height:100%;"></div>
        <!-- <dv-scroll-board :config="config" style="width:100%;height:30%" /> -->
    </div>

</template>

<script setup lang="ts">
import { onMounted, ref, reactive } from 'vue'
import * as echarts from 'echarts';
const chart = ref()

const config = reactive({
    header: ['列1', '列2', '列3'],
    data: [
        ['行1列1', '行1列2', '行1列3'],
        ['行2列1', '行2列2', '行2列3'],
        ['行3列1', '行3列2', '行3列3'],
        ['行4列1', '行4列2', '行4列3'],
        ['行5列1', '行5列2', '行5列3'],
        ['行6列1', '行6列2', '行6列3'],
        ['行7列1', '行7列2', '行7列3'],
        ['行8列1', '行8列2', '行8列3'],
        ['行9列1', '行9列2', '行9列3'],
        ['行10列1', '行10列2', '行10列3']
    ],
    index: true,
    columnWidth: [50],
    align: ['center']
})
// 基于准备好的dom，初始化echarts实例
onMounted(() => {
    console.log(chart.value);
    charInit()
})
function charInit() {
    var myChart = echarts.init(chart.value);
    const option = {
        title: {
            text: '巡查上报记录数量',
            textStyle: {
                color: '#fff',
                fontSize: 15
            }
        },
        // tooltip: {
        //     show:true,
        //     trigger:'axis',
        //     confine:false
        // },

        xAxis: {
            type: 'value',
            axisLine: {
                lineStyle: {
                    color: '#fff'
                }
            }
        },
        yAxis: {
            type: 'category',
            data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子'],
            axisLine: {
                lineStyle: {
                    color: '#fff'
                }
            }
        },
        series: [
            {
                name: '销量',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20],
                barWidth: 20,
                itemStyle: {
                    color: function (params: any) {
                        var colorList = ['#ffdb5c', '#ff9f7f', '#8378ea', '#32c5e9', '#e690d1', '#e7bcf3']
                        return colorList[params.dataIndex]
                    }
                }
            }
        ],
        toolbox: {   // 工具箱
            show: true,
            feature: {
                saveAsImage: {},
                dataView: { readOnly: false },
                restore: {},
                magicType: {
                    type: ['line', 'bar']
                }
            }
        }
    }
    // 绘制图表
    myChart.setOption(option);
}

</script>

<style scoped>
.main {
    width: 100%;
    height: 100%;

}

.chart {
    background: #093060;
}
</style>