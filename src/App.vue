<template>
  <div id="app">
    <img alt="Vue logo" width=50% src="./assets/spoton_logo_big.png">
    <StatesList></StatesList>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import StatesList from './components/StatesList.vue'

export default {
  name: 'app',
  components: {
    StatesList
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
