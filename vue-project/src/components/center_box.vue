

<script setup lang="js">
import chart_grass from '@/components/chart_grass.vue'

</script>
<template>
    <div class="top">
        <div class="topleft">
            <dv-border-box8>
                <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                    <div style="color: orange;font-size: 10px; text-align: left;">此处插入直播1</div>
                </div>
            </dv-border-box8>
        </div>
        <div class="topright">
            <dv-border-box8>
                <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                    <div style="color: orange;font-size: 10px; text-align: left;">此处插入直播2</div>
                </div>
            </dv-border-box8>
        </div>
    </div>
    <div class="bottom">
        <div class="bottomleft">
            <dv-border-box8>
                <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                    <div style="color: orange;font-size: 10px; text-align: left;">此处插入地图</div>
                </div>
            </dv-border-box8>
        </div>
        <div class="bottomright">
            <dv-border-box8>
                <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                    <chart_grass></chart_grass>
                </div>
            </dv-border-box8>
        </div>
    </div>
    <div class="middle">
        <dv-border-box12>
            <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
                <div style="color: orange;font-size: 10px; text-align: left;">此处插入图表</div>
            </div>
        </dv-border-box12>
    </div>
</template>

<style scoped lang="css">
.top {
    display: flex;
    width: 100%;
    height: 45%;
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
    height: 15%;
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