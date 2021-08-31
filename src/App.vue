<template>
  <h1>{{ title }} ⏱️</h1>
  <Block />
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {Block},
  data() {
    return {
      title: 'Vanheaven Reaction Timer'
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
  margin-top: 60px;
}
</style>
