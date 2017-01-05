<template>
  <div id="app">
    <heading></heading>
    <randomizer></randomizer>
  </div>
</template>

<script>
import Heading from './components/Header'
import Randomizer from './components/Randomizer'

export default {
  name: 'app',
  components: {
    Heading,
    Randomizer
  }
}
</script>

<style lang='scss'>
  $color--copy: #2c3e50;
  $color--accent: #c69;

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: $color--copy;
    margin-top: 60px;
  }
</style>
