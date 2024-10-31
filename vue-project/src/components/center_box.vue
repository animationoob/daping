

<script setup lang="js">
import utils from '@/components/videos/video.js'
import Video from '@/components/videos/video.vue'
import chart_grass from '@/components/chart_grass.vue'
import MapContainer from '@/components/MapContainer.vue'
import echarts from '@/components/echarts.vue'
import chart_down from '@/components/chart_down.vue'
</script>
<template>
    <div class="top">
        <div class="topleft">
            <dv-border-box8>
                <Video :signalingUrl="utils.signalingUrl" :roomId="utils.roomId1" :clientId="utils.clientId" />
            </dv-border-box8>
        </div>
        <div class="topright">
            <dv-border-box8>
                <Video :signalingUrl="utils.signalingUrl" :roomId="utils.roomId2" :clientId="utils.clientId" />
            </dv-border-box8>
        </div>
    </div>
    <div class="bottom">
        <div class="bottomleft">
            
                <MapContainer></MapContainer>
            
        </div>
        <div class="bottomright">
            <dv-border-box8>
                <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                    <chart_grass></chart_grass>
                    <echarts></echarts>
                </div>

            </dv-border-box8>
        </div>
    </div>
    <div class="middle">
        <dv-border-box12>
            <chart_down></chart_down>
        </dv-border-box12>
    </div>
</template>

<style scoped lang="css">
.top {
    display: flex;
    width: 100%;
    height: 35%;
    background-color: transparent;
}
.topleft {
    flex: 1; /* 左侧区域占据一半空间 */
    background-color: transparent;
}
.topright {
    flex: 1; /* 右侧区域占据一半空间 */
    background-color: transparent;
}
.middle {
    width: 100%;
    height: 20%;
    background-color: transparent; /* 设置背景颜色为透明 */
}
.bottom {
    display: flex; /* 使用 Flexbox 布局 */
    width: 100%;
    height: 45%;
}
.bottomleft {
    flex: 1; /* 左侧区域占据一半空间 */
    background-color: transparent;
}
.bottomright {
    flex: 1; /* 右侧区域占据一半空间 */
    background-color: transparent;
}
</style>