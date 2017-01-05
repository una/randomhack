<template>
  <h1>{{ title }}</h1>
</template>

<script>
export default {
  name: 'heading',
  data () {
    return {
      title: 'RanomHack Randomizer!'
    }
  }
}
</script>

<style scoped lang="scss">
  h1 {
    color: hotpink;
  }
</style>
