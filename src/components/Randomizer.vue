<template>
  <ul class="randomized-list">
    <li class="randomized-item"> {{ noun }} </li>
    <li class="randomized-item"> {{ emoji }} </li>
    <li class="randomized-item challenge-item"> with {{ challenge }} </li>
  </ul>
</template>

<script>
const Sentencer = require('sentencer');
const emojiList = require('emojilib/emojis.json');

const randomEmoji = function (obj) {
  var keys = Object.keys(obj)
  return (obj[keys[keys.length * Math.random() << 0]])['char'];
}

let challengeList = [ 'Ruby', 'JavaScript', 'Node', 'GO', 'Python', 'React', 'Vue.js', 'Hardware', 'Stylus', 'Offline-first', 'CSS Modules', 'Hapi', 'an API' ];

// configure randomized challenge item as Sentencer plugin
Sentencer.configure({
  actions: {
    challenge: function () {
      let randomLang = challengeList[Math.floor(Math.random() * challengeList.length)];
      return randomLang;
    }
  }
});

// randomizer component
export default {
  name: 'randomizer',
  data () {
    return {
      noun: Sentencer.make('-{ noun }-'),
      challenge: Sentencer.make('-{ challenge }-'),
      emoji: randomEmoji(emojiList)
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
