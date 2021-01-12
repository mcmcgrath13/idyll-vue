<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Idyll file="hello_world"/>
</template>

<script>
import Idyll from './components/Idyll.vue'

export default {
  name: 'App',
  components: {
    Idyll
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
