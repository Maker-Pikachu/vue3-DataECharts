<template>
    <div class="main">
        <ul>
            <li>
                <Gauge></Gauge>

            </li>
            <li>
                <Gauge></Gauge>
            </li>
            <li>
                <Gauge></Gauge>
            </li>
            <li>
                <Gauge></Gauge>
            </li>
        </ul>
        
    </div>
</template>

<script setup lang="ts">
import Gauge from './gauge.vue';


</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
}
.main{
    width: 100%;
    height: 100%;
   
}
.main ul{
    display: flex;
    justify-content: space-between;
    gap: 10px;

}
.main ul li{
    list-style-type:none;
    flex: 1;

}
</style>