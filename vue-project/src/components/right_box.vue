<script setup lang="js">
import wenList from '@/components/wenList.vue'
import chart from '@/components/chart.vue'
import chart_tem from '@/components/chart_tem.vue'
</script>

<template>
    <div class="top">
        
        <dv-border-box1  style="display: flex;height: 100%;">
            <div style="width: 100%;" h18rem color-white flex justify-center items-center>
                <strong style="color: orange; text-shadow: 2px 2px 4px #000000;">实时墒情信息</strong>
            </div>
            <chart></chart>


        </dv-border-box1>

    </div>
    <div class="bottom">
        
        <dv-border-box8  style="display: flex;height: 100%;">
            <wenList></wenList>
            <chart_tem></chart_tem>
        </dv-border-box8>
    </div>
</template>

<style scoped lang="css">
.top {
    width: 100%;
    height: 30%;
    background-color: transparent;
}

.bottom {
    width: 100%;
    height: 70%;
    background-color: rgb(0, 0, 0, 0);
}
</style>