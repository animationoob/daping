<script setup>
import { onMounted, onUnmounted } from "vue";
import AMapLoader from "@amap/amap-jsapi-loader";

let map = null;

onMounted(() => {
  window._AMapSecurityConfig = {
    securityJsCode: "bdc40abd3bceba3484a148a70cb63d2d",
  };
  AMapLoader.load({
    key: "adc42bb9d6bf9c8412304e5d7bb3fb7a", // 申请好的Web端开发者Key，首次调用 load 时必填
    version: "2.0", // 指定要加载的 JSAPI 的版本，缺省时默认为 1.4.15
    plugins: ["AMap.Scale"], //需要使用的的插件列表，如比例尺'AMap.Scale'，支持添加多个如：['...','...']
  })
    .then((AMap) => {
      map = new AMap.Map("container", {
        // 设置地图容器id
        viewMode: "3D", // 是否为3D地图模式
        zoom: 11, // 初始化地图级别
        center: [110.349,38.9568], // 初始化地图中心点位置
      });

      // 创建一个 Marker 实例
      const marker = new AMap.Marker({
        position: new AMap.LngLat(110.349,38.9568), //经纬度对象，也可以是经纬度构成的一维数组[116.39, 39.9]
        title: "北京",
      });

      // 将创建的点标记添加到已有的地图实例
      map.add(marker);
    })
    .catch((e) => {
      console.log(e);
    });
});

onUnmounted(() => {
  map?.destroy();
});
</script>

<template>
  <div id="container"></div>
</template>

<style scoped>
#container {
  width: 100%;
  height: 100%;
}
</style>