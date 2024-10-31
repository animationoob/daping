<template>
  <div ref="chartDom" style="width: 100%; height: 100%;"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue';
import * as echarts from 'echarts';

// 创建一个响应式引用来保存DOM元素
const chartDom = ref(null);
let chartInstance = null;

// 初始化ECharts实例并设置配置项（这里以折线图为例，但可灵活替换）
onMounted(async () => {
  await nextTick(); // 确保DOM已经渲染完成
  chartInstance = echarts.init(chartDom.value);
  const option = {
    title: {
      text: '植物生长曲线',
      left: 'center', // 设置标题居中
      textStyle: {
        color: '#fff', // 设置标题颜色为白色
      },
      padding: [10, 0, 20, 0] // 设置标题的内边距，向下移动10px
    },
    tooltip: {},
    xAxis: {
      data: ["类别1", "类别2", "类别3", "类别4", "类别5"]
    },
    yAxis: {},
    series: [{
      name: '数据系列',
      type: 'line', // 这里可以是'line'、'bar'、'pie'等，根据图表类型选择
      data: [80, 70, 85]
    }]
  };
  chartInstance.setOption(option);
});

// 销毁ECharts实例
onUnmounted(() => {
  if (chartInstance != null && chartInstance.dispose) {
    chartInstance.dispose();
  }
});
</script>

<style scoped>
/* 添加一些CSS样式来美化图表容器（可选） */
</style>