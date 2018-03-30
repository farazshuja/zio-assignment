<template>
  <div id="app">
    <input-container></input-container>
  </div>
</template>

<script>
import InputContainer from './components/InputContainer'

export default {
  name: 'app',
  components: {
    InputContainer
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
