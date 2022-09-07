<template>
  <div>计数原始:{{ number }}</div>
  <div>计数ref:{{ numberRef }}</div>
  <button @click="add">点我加1</button>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  name: 'HelloWorld',
  setup() {
    let number = 0
    let numberRef = ref(number)

    let person = reactive({
      name: 'name'
    })

    const add = () => {
      numberRef.value++
      console.log(number, numberRef)
      console.log(person)
    }

    return {
      number,
      person,
      numberRef,
      add
    }
  }
}
</script>
