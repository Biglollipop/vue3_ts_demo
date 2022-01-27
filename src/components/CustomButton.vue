<template>
  <div>
    <el-button type="primary" size="medium" >
      <slot>
        {{name}}
      </slot>
    </el-button>
  </div>
</template>

<script setup lang="ts">
import { withDefaults, defineProps, defineExpose } from 'vue'
interface Props {
  name:string
}
const props = withDefaults(defineProps<Props>(), {
  name: '提交'
})
defineExpose({
  props
})
</script>

<style>

</style>
