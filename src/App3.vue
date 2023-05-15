<script setup>
  import { ref, watch } from 'vue'
  const count = ref(0)
  const num = ref(0)
  const addCount = ()=>{
    count.value++
  }
  const addNum = ()=>{
    num.value++
  }
  // 侦听单个数据
  watch(count, (newval, oldval)=>{
    console.log('新值:',newval, '旧值:' , oldval)
  })
  // 侦听多个数据
  watch(
    [count, num],
    ([countNew, numNew],[countOld, numOld]) =>{
      console.log('count新值:',countNew, 'count旧值:' , countOld)
      console.log('num新值:',numNew, 'num旧值:' , numOld)
    }
  )
</script>

<template>

  <button @click="addCount">计数器：{{ count }}</button>
  <button @click="addNum">计数器：{{ num }}</button>

</template>