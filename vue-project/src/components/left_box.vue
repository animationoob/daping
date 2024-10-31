<template>
    <div class="top">
      <dv-border-box1>
        <div style="width: 100%;" h18rem color-white flex justify-center items-center>
          <strong style="color: orange;font-style: italic; text-shadow: 2px 2px 4px #000000;">信息发布</strong>
        </div>
        <div style="margin-top: 5px;margin-left: 15px;margin-bottom: 15px;">
          <div style="color: orange;margin:30px;font-size: 15px; text-align: left;">2024年10月18日，建设草原生态监测站。</div>
        </div>
      </dv-border-box1>
    </div>
    <div class="bottom">
      <dv-border-box13 style="height: 100%;
      width: 100%;padding-left: 10px;padding-bottom: 10px;
      padding-right: 10px;padding-top: 20px;
      position: relative;">
        <div class="left">
          <el-tree :data="forestData" :props="defaultProps" @node-click="handleNodeClick" />
        </div>
        <div class="right">
          <el-scrollbar style="height: 100%;width: 100%; justify-content: center;">
            <div style="text-align: left;color: orange;"><strong>设备列表</strong></div>
            <left_right_box v-for="(item, index) in deviceData" :key="index">
              <template #title>
                <div class="title" style="color: aliceblue;">{{ item.row1 }}
                <el-icon color="white" style="vertical-align: middle;">
                  <HelpFilled /></el-icon>{{ item.state }}</div>
              </template>
              <template #content>
                <div class="content" style="color: aliceblue;">{{ item.row2 }}
                  <span style="text-align: end;">{{ item.number }}</span>
                </div>
              </template>
            </left_right_box>
          </el-scrollbar>
        </div>
      </dv-border-box13>
    </div>
  </template>
  
  <script setup lang="js">
  import left_right_box from '@/components/left_right_box.vue'
  import { ref } from 'vue'
  import { HelpFilled } from "@element-plus/icons-vue"
  import forestDataJson from '@/assets/forest.json' // 导入forest.json文件
  import deviceDataJson from '@/assets/device.json' // 导入device.json文件
  
  const handleNodeClick = (data) => {
    console.log(data)
  }
  
  const forestData = ref(forestDataJson.data) // 使用导入的forest.json数据
  
  const defaultProps = {
    children: 'children',
    label: 'label',
  }
  
  const deviceData = ref(deviceDataJson) // 使用导入的device.json数据
  </script>
  
  <style scoped lang="css">
  .top {
    width: 100%;
    height: 30%;
    background-color: rgba(0, 0, 0, 0);
  }
  
  .bottom {
    width: 100%;
    height: 70%;
    background-color: rgba(0, 0, 0, 0);
  
    .left {
      position: absolute;
      display: flex;
      width: 50%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0);
    }
  
    .right {
      right: 0;
      position: absolute;
      display: flex;
      width: 50%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0);
    }
  }
  
  .el-tree {
    background: rgba(0, 0, 0, 0);
    width: 100%;
    font-size: 10px;
    color: aqua;
  }
  </style>