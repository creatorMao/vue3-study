<template>
  <div class="container-son">
    <div>{{ personInfo.name }}</div>
  </div>
</template>

<script>
import { inject } from 'vue'
export default {
  name: 'App',
  components: {},
  setup() {
    const personInfo = inject('personInfo')
    return {
      personInfo
    }
  }
}
</script>

<style scoped>
.container-son {
  height: 40px;
  background-color: yellow;
}
</style>
