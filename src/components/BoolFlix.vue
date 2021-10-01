<template>
  <div class="hello">
    <Searchbar @search="cercaFiltro"/>
    <Results :testoRicercato="testoRicercato"/>
  </div>
</template>

<script>
import Searchbar from '../components/Searchbar.vue';
import Results from '../components/Results.vue';
// import axios from "axios";

export default {
  name: 'BoolFlix',

   components :{
    Searchbar,
    Results,
  },

  data : function(){
      return {
          testoRicercato:"",
      }
  },

  methods : {
    cercaFiltro : function(ricerca){
      this.testoRicercato = ricerca;
      console.log(this.testoRicercato)
    }
  },

}
</script>

<style scoped lang="scss">

</style>
