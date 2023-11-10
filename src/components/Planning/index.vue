

<template>
  <div class="planning">
    <div class="container mt-5 ml-[150px]">
      <div> pag {{ roomID }}</div>
      <component :is="menuList[roomID[0]]?.page" />
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue'
import Bathroom from './Bathroom.vue'
import Entrance from './Entrance.vue'
import { PriceTag, House, Monitor, ReadingLamp, KnifeFork, ToiletPaper, Sunny } from '@element-plus/icons-vue'

const menuList = [
  { id: 'Entrance', name: '玄關', icon: PriceTag, page: Entrance },
  { id: 'LivingRoom', name: '客廳', icon: House, page: Entrance },
  { id: 'Study', name: '書房', icon: Monitor, page: Entrance },
  { id: 'Bedroom1', name: '主臥', icon: ReadingLamp, page: Entrance },
  { id: 'Bedroom2', name: '次臥', icon: ReadingLamp, page: Entrance },
  { id: 'Kitchen', name: '廚房', icon: KnifeFork, page: Entrance },
  { id: 'Bathroom', name: '浴室', icon: ToiletPaper, page: Bathroom },
  { id: 'Balcony', name: '陽台', icon: Sunny, page: Entrance }
]
const roomID = inject('roomID')

const menu = [
  { id: 0, name: '房屋資訊'},
  { id: 1, name: '需求整理'},
]
const pageID = inject('pageID')
const switchPage = (id) => {
  pageID.value = id
}
</script>

<style>
.planning {
  margin-left: 150px;
}
.planning h5 {
  padding-top: 20px;
  color: #f0b401;
}
</style>
