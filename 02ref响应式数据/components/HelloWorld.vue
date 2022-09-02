<template>
  {{ name }}
  <button @click="changeName">修改data选项里的name</button>

  {{ age }}
  <button @click="changeAge">修改通过setup返回的age</button>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HelloWorld',
  data() {
    return {
      name: '毛'
    }
  },
  props: {
    msg: String
  },
  methods: {
    changeName() {
      console.log('1')
      this.name = '陈'
    }
  },
  setup() {
    let age = ref(18)
    let schoolInfo = ref({
      name: '杭州大学'
    })
    console.log(schoolInfo)
    console.log(age)

    function changeAge() {
      console.log(age)
      age.value = 20
      console.log(age)
    }

    return {
      age,
      changeAge
    }
  }
}
</script>
