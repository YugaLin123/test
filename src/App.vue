<template>

  <el-container style="height: 100vh">
    <el-header><Header/></el-header>
    <el-container>
      <el-aside v-if="pageID" width="150px"><Aside/></el-aside>
      <el-main>
        <HelloWorld v-if="!pageID" msg="Vite + Vue" />
        <Planning v-else/>
      </el-main>
    </el-container>
  </el-container>
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Planning from './components/Planning/index.vue'
import Aside from './components/Planning/Aside.vue'
import { ref, provide } from 'vue'

const pageID = ref(1)
provide('pageID', pageID)
const roomID = ref([0,''])
provide('roomID', roomID)

</script>

<style scoped>
header {
  position: fixed;
  z-index: 50;
  width: 100%;
  padding: 0;
}
aside {
  position: fixed;
  z-index: 49;
  width: 150px;
  height: 100vh;
  padding-top: 60px;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
