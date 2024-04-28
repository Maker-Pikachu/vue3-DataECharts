<template>
    
    <div class="mian">
        <HeaderNav class="title"></HeaderNav>
        <div class="list">
            <ul>
                <li class="li">
                    <div>桥梁</div>
                    <div class="sp">
                        <span class="sp1">3232</span>
                        <span clsaa="sp2">个</span>
                    </div>
                </li>
                <li class="li">
                    <div>桥梁</div>
                    <div class="sp">
                        <span class="sp1">3232</span>
                        <span clsaa="sp2">个</span>
                    </div>
                </li>
                <li class="li">
                    <div>桥梁</div>
                    <div class="sp">
                        <span class="sp1">3232</span>
                        <span clsaa="sp2">个</span>
                    </div>
                </li>
                <li class="li">
                    <div>桥梁</div>
                    <div class="sp">
                        <span class="sp1">3232</span>
                        <span clsaa="sp2">个</span>
                    </div>
                </li>
                <li class="li">
                    <div>桥梁</div>
                    <div class="sp">
                        <span class="sp1">3232</span>
                        <span clsaa="sp2">个</span>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script setup lang="ts">
import HeaderNav from '@/components/headerNav.vue';
</script>

<style scoped>
.main{
    width: 100%;
    height: 100px;
    display: flex;
    flex-direction: column;

    color: #fff;
}
.title{
    height: 40%;
    text-align: center;
}
.list{
    height: 60%;
}
.list ul{
    width: 100%;
    height: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.list ul li{
    flex: 1;
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    background: #093060;
    text-align: center;
    border-right:1px solid #fff;
}
.list ul li div{
    height: 30px;
    font-size: 20px;
    line-height: 30px;
}
.sp1{
    font-size: 25px;
    font-weight: bold;
    padding-right: 10px;
}
.list ul li:nth-child(3n+1) .sp1{
    color:#ca0b0b
}
.list ul li:nth-child(3n+2) .sp .sp1{
    color:#eb8f0e
}
.list ul li:nth-child(3n+3) .sp .sp1{
    color:#12bfea
}
</style>