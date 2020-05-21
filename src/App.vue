<template>
  <div id="app">
    <DrumMachine msg="Drum Machine"/>
  </div>
</template>

<script>
import DrumMachine from './components/DrumMachine.vue'

export default {
  name: 'app',
  components: {
    DrumMachine
  }
}
</script>

<style>

html, body {
  height: 100%;
  margin: 0px;
  font-family: 'Raleway', sans-serif;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
