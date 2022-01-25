<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <el-button type="primary" @click="submitHandle">提交</el-button>
  </div>
</template>

<script setup lang="ts">
import { defineExpose, defineProps, defineEmits } from 'vue'
const props = defineProps<{
  msg:string
}>()
// eslint-disable-next-line func-call-spacing
const emit = defineEmits<{
  (e:'clickHandle', msg:string):void
}>()
const submitHandle = () => {
  emit('clickHandle', props.msg)
}
defineExpose({
  props
})
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
