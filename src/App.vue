<template>
  <h1>
    {{ title }}
  </h1>
</template>

<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      title: '나의 첫번째 vue3'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
