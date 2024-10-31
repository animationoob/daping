<template>
  <div class="table-container">
    <el-table
      :data="tableData"
      height="90%"
      style="width: 90%"
      :header-cell-style="{ 'background-color': 'transparent', 'color': 'white' }"
    >
      <el-table-column prop="date" label="属性" width="150" />
      <el-table-column prop="name" label="数值" width="150" />
      <el-table-column prop="address" label="其他" />
    </el-table>
  </div>
</template>

<script lang="ts" setup>
import tableDataJson from '@/assets/shangqing.json' // 导入tableData.json文件

const tableData = tableDataJson; // 使用导入的JSON数据
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