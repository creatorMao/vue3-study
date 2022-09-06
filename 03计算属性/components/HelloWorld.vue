<template>
  <div>名字：<input type="text" v-model="person.name" /></div>
  <div>爱好：<input type="text" v-model="person.hobby" /></div>
  <div>交友语录：{{ words }}</div>
</template>

<script>
import { reactive, computed } from 'vue'

export default {
  name: 'HelloWorld',
  setup() {
    const person = reactive({
      name: '',
      hobby: ''
    })

    const words = computed(() => {
      return `我叫${person.name},我是爱${person.hobby}小哥哥一枚啊！`
    })

    return {
      person,
      words
    }
  }
}
</script>
