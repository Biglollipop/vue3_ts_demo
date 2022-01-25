<template>
  <div class="home">
    <HelloWorld @click-handle="clickHandle" msg="Welcome to Your Vue.js + TypeScript App"/>
    <span>{{msg}}</span>
  </div>
</template>

<script setup lang="ts">
import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from 'vue'
const msg = ref <string>('')
const clickHandle = (val:string) => {
  console.log('val ', val)
  msg.value = val
}
</script>
