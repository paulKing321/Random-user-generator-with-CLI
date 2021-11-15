<template>
  <div id="app">
    <random-user/>
  </div>
</template>

<script>
import randomUser from './components/randomUser.vue'

export default {
  name: 'App',
  components: {
    randomUser
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: black;
  width: 100%;
  min-height: 100%;
  /* margin-top: 60px; */
}
</style>
