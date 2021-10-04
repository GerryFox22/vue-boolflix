<template>
  <div class="hello">
    <Searchbar @search="cercaFiltro"/>
    <Results :dataTeleFilms="dataTeleFilms" :dataFilms="dataFilms"/>
  </div>
</template>

<script>
import Searchbar from '../components/Searchbar.vue';
import Results from '../components/Results.vue';
import axios from "axios";

export default {
  name: 'BoolFlix',

   components :{
    Searchbar,
    Results,
  },

  data : function(){
      return {
          dataFilms:[],
          dataTeleFilms:[],
      }
  },

  methods : {
    cercaFiltro : function(ricerca){
       axios.get("https://api.themoviedb.org/3/search/movie?api_key=101cc2fb5e4661f4747b2caae74d2081&query=" + ricerca)
            .then((response) => {

            this.dataFilms = response.data.results
            console.log(this.dataFilms)
          
            })
            axios.get("https://api.themoviedb.org/3/search/tv?api_key=101cc2fb5e4661f4747b2caae74d2081&query=" + ricerca)
            .then((response) => {

            this.dataTeleFilms = response.data.results
             console.log(this.dataTeleFilms)
            })
    }
  },

}
</script>

<style scoped lang="scss">

</style>
