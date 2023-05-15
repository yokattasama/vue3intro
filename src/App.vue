<!-- <script>
import { ref } from 'vue'
export default {
  setup() {
    const count = ref(0)
    const addCount = () => {
      console.log('计数器++')
      count.value++
    }
    console.log('执行了 setup 函数')
    return {
      count,
      addCount
    }
  },
  beforeCreate() {
    console.log('beforeCreate')
  },
  
}
</script> -->

<script setup>
  import { ref } from 'vue'
  const message = '这是一段信息'
  const showMessage = () =>{
    console.log(message)
  }
  const count = ref(0)
  const addCount = () => {
    console.log('计数器++')
    count.value++
  }
</script>

<template>
  <button @click="addCount">计数器{{ count }}</button>
  <button @click="showMessage">打印信息</button>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
