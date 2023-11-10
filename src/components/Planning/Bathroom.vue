

<template>
  <div>
    <div> 浴室 </div>
    <div> pag {{ roomID }}</div>
  </div>
</template>

<script setup>
import { inject } from 'vue'
const roomID = inject('roomID')

</script>

<style scoped>

</style>
