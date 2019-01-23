<template>
  <div id="app">
    <Home msg="Solveur de contraintes"/>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>

<style>
  @import 'style/style.css';
</style>
