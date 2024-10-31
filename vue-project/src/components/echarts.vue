<template>
    <div class="grid-container">
      <!-- 其他内容可以放在这里 -->
      <div class="chart-container" ref="chartDom"></div>
    </div>
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
        text: ' ',
        textStyle: {
          color: '#fff' // 设置标题文字颜色为白色
        }
      },
      tooltip: {
        trigger: 'axis',
        textStyle: {
          color: '#fff' // 设置提示框文字颜色为白色
        }
      },
      legend: {
        data: ['草原面积', '主要植株', '生长高度', '植物覆盖率'],
        textStyle: {
          color: '#fff' // 设置图例文字颜色为白色
        }
      },
      grid: {
        left: '3%',
        right: '4%',
        bottom: '1%',
        containLabel: true
      },
      toolbox: {
        feature: {
          saveAsImage: {}
        }
      },
      xAxis: {
        type: 'category',
        boundaryGap: false,
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
        axisLabel: {
          textStyle: {
            color: '#fff' // 设置x轴标签文字颜色为白色
          }
        }
      },
      yAxis: {
        type: 'value',
        axisLabel: {
          textStyle: {
            color: '#fff' // 设置y轴标签文字颜色为白色
          }
        }
      },
      series: [
        {
          name: '草原面积',
          type: 'line',
          stack: 'Total',
          data: [220, 182, 191, 234, 290, 330, 310]
        },
        {
          name: '主要植株',
          type: 'line',
          stack: 'Total',
          data: [150, 232, 201, 154, 190, 330, 410]
        },
        {
          name: '生长高度',
          type: 'line',
          stack: 'Total',
          data: [320, 332, 301, 334, 390, 330, 320]
        },
        {
          name: '植物覆盖率',
          type: 'line',
          stack: 'Total',
          data: [820, 932, 901, 934, 1290, 1330, 1320]
        }
      ]
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
  .grid-container {
    display: grid;
    height: 100vh; /* 使用视口高度 */
    grid-template-rows: 1fr 50%; /* 上部内容占据剩余空间，下部内容占据50% */
  }
  
  .chart-container {
    /* 确保图表容器填满分配给它的网格空间 */
    height: 50%;
    width: 100%;
  }
  
  /* 添加一些CSS样式来美化图表容器（可选） */
  </style>