<template>
    <div class="table-container">
      <el-table
        :data="tableData"
        height="90%"
        style="width: 90%"
        :header-cell-style="{ 'background-color': 'transparent', 'color': 'white' }"
      >
        <el-table-column prop="date" label="属性" width="100" />
        <el-table-column prop="name" label="数值" width="100" />
        <el-table-column prop="address" label="其他" />
      </el-table>
    </div>
    <div style="width: 100%;height: 70%;margin-bottom: 5px;display: flex"></div>
  </template>
  
  <script lang="ts" setup>
  const tableData = [
    {
      date: '温度',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '湿度',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '风速',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '风向',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '气压',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '光照',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },
    {
      date: '降雨量',
      name: 'Tom',
      address: 'No. 189, Grove St, Los Angeles',
    },

    // ... 其他数据项
  ];
  </script>
  
  <style scoped>
  .table-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  
  .el-table {
    --el-table-border-color: transparent;
    --el-table-text-color: #bdbdbe;
    --el-table-header-text-color: white; /* 设置表头文字颜色为白色 */
    --el-table-row-hover-bg-color: transparent;
    --el-table-current-row-bg-color: transparent;
    --el-table-header-bg-color: transparent; /* 设置表头背景颜色为透明 */
    --el-table-bg-color: transparent;
    --el-table-tr-bg-color: transparent;
    --el-table-expanded-cell-bg-color: transparent;
  }
  
  /* 覆盖 header-cell-style 的背景色和文字颜色 */
  .el-table__header-wrapper thead tr th {
    background-color: transparent !important;
    color: white !important;
  }
  </style>