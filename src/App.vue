<template>
  <div id="app">
    <!--<div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>-->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="sass">
  *
    margin: 0
    padding: 0
    text-decoration: none
    box-sizing: border-box

  img
    vertical-align: top

  body
    font-family: 'Arial', 'sans-serif'
</style>
