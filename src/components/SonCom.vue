<script setup>
const props = defineProps({
    msg: String,
    count: Number
  })
const emits = defineEmits(['get-message'])
// 若要使用 props 值，创建一个变量接收即可
const random = () => {
  emits('get-message', '哈哈哈哈哈哈')
}
const txt = '这是一条子组件内部的信息，可以通过 defineExpose 暴露给父组件'
defineExpose({
  txt
})
</script>

<template>

  <h1>{{ msg }}</h1>
  <h2>{{ count }}</h2>

  <button @click="random">子组件传递数据</button>

</template>