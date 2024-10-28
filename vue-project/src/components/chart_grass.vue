<template>
    <div class="table-container">
      <el-table
        :data="tableData"
        height="90%"
        style="width: 90%"
        :header-cell-style="{ 'background-color': 'transparent', 'color': 'white', 'font-size': '16px' }"
      >
        <el-table-column prop="date" label="属性" width="520" />
        <el-table-column prop="name" label="数值" width="0" />
      </el-table>
    </div>
  </template>
  
  <script lang="ts" setup>
  const tableData = [
    {
      date: '草原面积',
      name: '10000平方米',
    },
    {
      date: '主要植株',
      name: '草',
    },
    {
      date: '生长高度',
      name: '3米',
    },
    {
      date: '植被覆盖率',
      name: '80%',
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
    font-size: 20px; /* 设置表格中文字的默认大小 */
  }
  
  /* 设置表头文字大小 */
  .el-table__header-wrapper thead tr th {
    background-color: transparent !important;
    color: white !important;
    font-size: 25px !important; /* 设置表头文字大小 */
  }
  
  /* 如果需要设置单元格内容的文字大小，可以添加以下样式 */
  .el-table .cell {
    font-size: 20px; /* 设置单元格内容文字大小 */
  }
  </style>