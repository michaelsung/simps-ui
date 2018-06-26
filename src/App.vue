<template>
  <div id="app">
    <AppContainer />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import AppContainer from './components/AppContainer.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    AppContainer
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
  margin-top: 0px;
}
</style>
