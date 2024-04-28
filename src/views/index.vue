<template>
    
    <div class="container">
        <ChartsFirst class="item item1"></ChartsFirst>
        <ChartsSecond class="item item2"></ChartsSecond>
        <ChartsThird class="item item3"></ChartsThird>
        <ChartsFour class="item item4"></ChartsFour>
    </div>
    
</template>

<script setup lang="ts">

import ChartsFirst from '@/components/chartsFirst.vue';
import ChartsSecond from '@/components/chartsSecond.vue';
import ChartsThird from '@/components/chartsThird.vue';
import ChartsFour from '@/components/chartsFour.vue';
</script>

<style scoped >
.container{
    display: grid;
    width: 100%;
    height: 100%;
    grid-template-columns: 1fr 4fr;
    grid-template-rows: 2fr 3fr 2fr;
    gap: 10px;
    
}
.item{

    color: #fff;
}
.item1{
    grid-column: 1 / 3;
}
.item2{
    grid-row: 2/4;
}
</style>