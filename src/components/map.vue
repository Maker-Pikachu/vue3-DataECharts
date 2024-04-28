<template>
    <div class="mian">
        <div class="chart" ref="chart" style="width: 100%;height:100%;"></div>
    </div>

</template>

<script setup lang="ts">
import { onMounted, ref, reactive } from 'vue'
import * as echarts from 'echarts';
const chart = ref()
// 基于准备好的dom，初始化echarts实例
onMounted(() => {
    charInit()
})
function charInit() {
    var myChart = echarts.init(chart.value);
    const option = {
     
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