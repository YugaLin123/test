

<template>
  <nav class="navbar navbar-expand-sm bg-light justify-content-center">
    <ul class="navbar-nav">
      <li class="nav-item" v-for="item in menu" key="item">
        <a class="nav-link" href="#" @click="switchPage(item.id)"> {{ item.name }}</a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { inject } from 'vue'

const menu = [
  { id: 0, name: '房屋資訊'},
  { id: 1, name: '需求整理'},
]
const pageID = inject('pageID')
const switchPage = (id) => {
  pageID.value = id
}
</script>

<style scoped>

</style>
