<template>
  <div v-if="flag">计数1:{{ number1 }}</div>
  <button @click="add1">点我加1</button>
  <button @click="hide">点我显示或者隐藏</button>
</template>

<script>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted
} from 'vue'

export default {
  name: 'HelloWorld',
  setup() {
    let number1 = ref(0)
    let flag = ref(true)

    const add1 = () => {
      number1.value++
    }

    const hide = () => {
      flag.value = !flag.value
    }

    onBeforeMount(() => {
      console.log('setup里的onBeforeMount')
    })

    onMounted(() => {
      console.log('setup里的onMounted')
    })

    onBeforeUpdate(() => {
      console.log('setup里的onBeforeUpdate')
    })

    onUpdated(() => {
      console.log('setup里的onUpdated')
    })

    onBeforeUnmount(() => {
      console.log('setup里的onBeforeUnmount')
    })

    onUnmounted(() => {
      console.log('setup里的onUnmounted')
    })

    return {
      number1,
      add1,
      flag,
      hide
    }
  }
}
</script>
