<template>
  <div class="Results">
      {{testoRicercato}}
  </div>
</template>

<script>

export default {
    name :"Results",
    props :["testoRicercato"],
  
}
</script>

<style lang="scss" scoped>
.Results {
    background-color: gray;
    height: 50vh;
}
</style>