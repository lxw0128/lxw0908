<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>学生快速换班</h1>
    <router-link to="/"> Welcome</router-link>
    <router-link to="/changeclass"> Changeclass</router-link>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
