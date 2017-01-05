<template>
  <ul class="randomized-list">
    <li class="randomized-item"> {{ adj }} </li>
    <li class="randomized-item"> {{ noun }} </li>
  </ul>
</template>

<script>
var Sentencer = require('sentencer');

export default {
  name: 'randomizer',
  data () {
    return {
      adj: Sentencer.make('-{ adjective }-'),
      noun: Sentencer.make('-{ noun }-')
    }
  }
}
</script>

<style scoped lang="scss">
  .randomized-list {
    font-size: 2em;
    list-style: none;
  }

  .randomized-item {
    display: inline-block;
  }
</style>
