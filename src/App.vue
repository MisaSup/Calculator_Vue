<template>
  <img class="vue_logo" alt="Vue logo" src="./assets/logo.png">
  <calc-wrapper/>
</template>

<script>
import CalcWrapper from "./components/CalcWrapper.vue"

export default {
  name: 'App',
  components: {
    CalcWrapper
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
  margin-top: 40px;
}
.vue_logo {
  width: 50px;
}
</style>
