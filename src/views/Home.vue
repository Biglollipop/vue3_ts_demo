<template>
  <div class="home">
    <HelloWorld @click-handle="clickHandle" msg="Welcome to Your Vue.js + TypeScript App"/>
    <span>{{msg}}</span>
    <hr>
    <el-select v-model="value" @change="changeHangle" placeholder="请选择">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
      </el-option>
    </el-select>
    <hr>
    <CustomButton>
      <template v-slot:default>
        {{changeName}}
      </template>
    </CustomButton>
  </div>
</template>

<script setup lang="ts">
import HelloWorld from '@/components/HelloWorld.vue'
import CustomButton from '@/components/CustomButton.vue'

import { reactive, ref, defineExpose, toRefs } from 'vue'

const msg = ref <string>('')

const value = ref <string>('')

const options = reactive <any>([
  {
    label: '提交',
    value: '提交'
  },
  {
    label: '保存',
    value: '保存'
  },
  {
    label: '新增',
    value: '新增'
  },
  {
    label: '删除',
    value: '删除'
  },
  {
    label: '编辑',
    value: '编辑'
  }
])

const clickHandle = (val:string) => {
  msg.value = val
}
const changeName = ref<string>('提交')
const changeHangle = (val:string) => {
  changeName.value = val
}

defineExpose({
  value,
  clickHandle,
  ...toRefs(options),
  changeHangle,
  changeName
})
</script>
