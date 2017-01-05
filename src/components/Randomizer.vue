<template>
  <ul class="randomized-list">
    <li class="randomized-item"> {{ adj }} </li>
    <li class="randomized-item"> {{ noun }} </li>
    <li class="randomized-item challenge-item"> with {{ challenge }} </li>
  </ul>
</template>

<script>
const Sentencer = require('sentencer');
let challengeList = [ 'Ruby', 'JavaScript', 'Node', 'GO', 'Python', 'React', 'Vue.js', 'Hardware', 'Stylus', 'Offline-first', 'CSS Modules', 'Hapi', 'an API' ];

Sentencer.configure({
  actions: {
    challenge: function () {
      let randomLang = challengeList[Math.floor(Math.random() * challengeList.length)];
      return randomLang;
    }
  }
});

export default {
  name: 'randomizer',
  data () {
    return {
      adj: Sentencer.make('-{ adjective }-'),
      noun: Sentencer.make('-{ noun }-'),
      challenge: Sentencer.make('-{ challenge }-')
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

  .challenge-item {
    background: yellow;
  }
</style>
