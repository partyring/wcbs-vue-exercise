<template>
  <div id="app">
    <Countries msg="Listing Countries by Danielle Platt @party-ring"/>
  </div>
</template>

<script>
import Countries from './components/Countries.vue'

export default {
  name: 'app',
  components: {
    Countries
  }
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
