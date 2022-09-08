<template>
  <div class="container-child">
    <div>{{ personInfo.age }}</div>
    <Son />
  </div>
</template>

<script>
import Son from '@/components/Son.vue'
import { inject } from 'vue'
export default {
  name: 'App',
  components: {
    Son
  },
  setup() {
    const personInfo = inject('personInfo')
    return {
      personInfo
    }
  }
}
</script>

<style scoped>
.container-child {
  height: 80px;
  background-color: blue;
}
</style>
