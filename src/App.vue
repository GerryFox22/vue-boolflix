<template>
  <div id="app">
    <!-- Font awesome --> 
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"/>

    <BoolFlix />
  </div>
</template>

<script>
import BoolFlix from './components/BoolFlix.vue'

export default {
  name: 'App',
  components: {
    BoolFlix,
  }
}
</script>

<style lang="scss">
@import "style/general.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

}
</style>
