<template>
  <div class="table-container">
    <el-table
      :data="tableData"
      height="90%"
      style="width: 90%"
      :header-cell-style="{ 'background-color': 'transparent', 'color': 'white' }"
    >
      <el-table-column prop="date" label="属性" width="350" />
      
      <el-table-column prop="address" label="其他" />
    </el-table>
  </div>
</template>

<script lang="ts" setup>
const tableData = [
  {
    date: '草原面积',
    
    address: '5000㎡',
  },
  {
    date: '主要植株',
     address: '仙人掌',
  },
  {
    date: '生长高度',
     address: '0.4m',
  },
  {
    date: '植被覆盖率',
     address: '98.77%',
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