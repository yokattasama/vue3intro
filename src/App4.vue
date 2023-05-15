<script setup>
  import { ref, watch } from 'vue'
  const info = ref({
    name: 'zs',
    age: 10
  })
  const changeAge = ()=>{
    info.value.age++
  }
  const chanageName = ()=>{
    info.value.name = 'z'+Math.ceil(Math.random()*10)
  }
  const state = ref({ count: 0 })
  const changeState = () => {
    state.value.count++
  }
  // 深度侦听 开启deep
  watch(state, ()=>{
    console.log('对象属性值发生变化')
  },{
    deep: true
  })
  // 精确侦听 第一个参数函数中返回要侦听的属性 无需开启deep
  watch(
    ()=>info.value.name,
    (newval, oldval)=>{
      console.log(`新name${newval}, 旧name${oldval}`)
    }
  )
</script>

<template>

  <button @click="changeState">{{ state.count }}</button>

  <button @click="chanageName">改变名称按钮</button>
  <button @click="changeAge">改变年龄按钮</button>

</template>