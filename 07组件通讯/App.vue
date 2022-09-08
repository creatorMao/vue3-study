<template>
  <div class="container">
    <Child />
  </div>
</template>

<script>
import Child from '@/components/Child.vue'
import { reactive, provide } from 'vue'
export default {
  name: 'App',
  components: {
    Child
  },
  setup() {
    let personInfo = reactive({
      name: '毛',
      age: 25
    })

    provide('personInfo', personInfo)
  }
}
</script>

<style scoped>
.container {
  height: 100px;
  background-color: gray;
}
</style>
