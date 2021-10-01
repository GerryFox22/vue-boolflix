<template>
  <div id="app">
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
