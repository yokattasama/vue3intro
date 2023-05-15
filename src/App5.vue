<script setup>
import { ref, onMounted } from 'vue'
import SonCom from './components/SonCom.vue';
onMounted(()=>{
  console.log('组件挂载完成1')
})
onMounted(()=>{
  console.log('组件挂载完成2')
})
const count = ref(80)
const addCount = ()=>{
  console.log('增加计数')
  count.value++
}
const consoleMsg = (msg)=>{
  console.log(`从子组件接收来的信息${msg}`)
}
const ref1 = ref(null)
const ref2 = ref(null)

onMounted(()=>{
  console.log(ref1.value, 'dom')
  console.log(ref2.value, 'dom')
})
</script>
<template>
  <div>
    <div ref="ref1">Aloha!!!!!!!!!!!!!!!</div>

    <SonCom ref="ref2" :count="count" msg="哈哈哈哈" @get-message="consoleMsg"></SonCom>

    <button @click="addCount">计数器增加数值</button>

    <button @click="getDom">获取组件</button>
  </div>

</template>