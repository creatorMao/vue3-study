<template>
  <div>计数1:{{ number1 }}</div>
  <button @click="add1">点我加1</button>
  <br />
  <div>计数2:{{ number2 }}</div>
  <button @click="add2">点我加1</button>
  <br />

  <div>姓名：{{ personInfo.name }}</div>
  <button @click="alterName">点我修改用户名称</button>
  <br />
  <div>英语成绩:{{ personInfo.scores.english.score }}</div>
  <button @click="alterScore">求求你，让我及格吧</button>
</template>

<script>
import { ref, watch, reactive } from 'vue'

export default {
  name: 'HelloWorld',
  setup() {
    let number1 = ref(0)
    let number2 = ref(0)
    const personInfo = reactive({
      name: '毛',
      scores: {
        english: {
          score: 59
        }
      }
    })

    const add1 = () => {
      number1.value++
    }

    const add2 = () => {
      number2.value++
    }

    const alterName = () => {
      personInfo.name += '~'
    }

    watch([number1, number2], (newValue, oldValue) => {
      console.log(newValue, oldValue) //[1, 0] [0, 0]
    })

    // watch(
    //   personInfo,
    //   (newValue, oldValue) => {
    //     console.log(newValue, oldValue)
    //   },
    //   {
    //     deep: false
    //   }
    // )

    // watch(
    //   () => {
    //     return personInfo.name
    //   },
    //   (newValue, oldValue) => {
    //     console.log(newValue, oldValue)
    //   }
    // )

    watch(
      () => {
        return personInfo.scores
      },
      (newValue, oldValue) => {
        console.log(newValue, oldValue)
      },
      {
        deep: true
      }
    )

    const alterScore = () => {
      personInfo.scores.english.score += 1
    }

    return {
      number1,
      add1,
      number2,
      add2,
      personInfo,
      alterName,
      alterScore
    }
  }
}
</script>
