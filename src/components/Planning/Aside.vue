<template>
  <el-scrollbar>
    <el-menu class="menu" default-active="0" 
    @open="handleOpen">
      <el-menu-item v-for="(menuItem, menuIndex) in menuList" key="menuIndex" :index="menuIndex.toString()">
        <el-icon><component :is="menuItem.icon" /></el-icon>
        <span>{{menuItem.name}}</span>
      </el-menu-item>
    </el-menu>
  </el-scrollbar>
</template>

<script setup>
import { PriceTag, House, Monitor, ReadingLamp, KnifeFork, ToiletPaper, Sunny } from '@element-plus/icons-vue'
import { inject } from 'vue'
const menuList = [
  { id: 'Entrance', name: '玄關', icon: PriceTag },
  { id: 'LivingRoom', name: '客廳', icon: House },
  { id: 'Study', name: '書房', icon: Monitor },
  { id: 'Bedroom1', name: '主臥', icon: ReadingLamp },
  { id: 'Bedroom2', name: '次臥', icon: ReadingLamp },
  { id: 'Kitchen', name: '廚房', icon: KnifeFork },
  { id: 'Bathroom', name: '浴室', icon: ToiletPaper },
  { id: 'Balcony', name: '陽台', icon: Sunny }
]
const roomID = inject('roomID')
// const subMenuList = [
//   { id: 's0', name: '家具/家電需求' },
//   { id: 's1', name: '風格/特殊需求' },
//   { id: 's2', name: '示意圖' },
//   { id: 's3', name: '購買連結' },
// ]
const handleOpen = (key) => {
  console.log(key)
  roomID.value = [key, '']
}

</script>

<style>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 150px;
  min-height: 400px;
}
.menu {
  min-height: 100vh;
}
.el-menu-item {
  justify-content: center;
}
</style>
