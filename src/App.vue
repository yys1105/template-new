<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="stylus">
  *
    padding 0
    margin 0
  html,
  body
    height 100%
  #app
    height 100%
    background-color #c7c7c7
</style>
