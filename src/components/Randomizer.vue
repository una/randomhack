<template>
  <ul class="randomized-list">
    <li class="randomized-item"> {{ noun }} </li>
    <li class="randomized-item"> {{ emoji }} </li>
    <li class="randomized-item"> <small>with</small> <span class="challenge-item">{{ challenge }} </span> </li>
  </ul>
</template>

<script>
const Sentencer = require('sentencer');
const emojiList = require('emojilib/emojis.json');

// get random emoji from EmojiLib json except for flags (last 209 items)
const randomEmoji = function (obj) {
  var keys = Object.keys(obj)
  return (obj[keys[(keys.length - 209) * Math.random() << 0]])['char'];
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
    font-size: 3em;
    list-style: none;
  }

  .randomized-item {
    display: inline-block;
  }

  .challenge-item {
    background: yellow;
  }

  small {
    font-size: 70%;
    vertical-align: middle;
  }
</style>
