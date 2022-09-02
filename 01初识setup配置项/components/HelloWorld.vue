<template>
  <h1>姓名{{ name }}</h1>
  <h1>姓名{{ age }}</h1>
  <button @click="showName">展示我</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  setup: function () {
    const name = '毛致武'
    const age = 18

    function showName() {
      alert(name)
    }

    return {
      name,
      age,
      showName
    }
  }
}
</script>
