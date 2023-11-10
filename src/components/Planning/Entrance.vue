

<template>
  <div>
    <div>玄關</div>
    <div>pag {{ roomID }}</div>
    <h5>家具/家電需求</h5>
      <ol>
        <li>鞋櫃：保留12~15雙鞋子的空間</li>
        <li>不需要污衣櫃</li>
        <li>放鑰匙區＋一個插座＋燈</li>
        <li>安全帽兩頂的空間</li>
        <li>收納：衛生紙、清潔用品、醫療箱、滅火器</li>
      </ol>
    <h5>風格/特殊需求</h5>
    <h5>示意圖</h5>
    <h5>購買連結</h5>
  </div>
</template>

<script setup>
import { inject } from 'vue'
const roomID = inject('roomID')

// const subMenuList = [
//   { id: 's0', name: '家具/家電需求' },
//   { id: 's1', name: '風格/特殊需求' },
//   { id: 's2', name: '示意圖' },
//   { id: 's3', name: '購買連結' },
// ]
</script>

<style scoped>

</style>
