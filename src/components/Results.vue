<template> 
    <div class="results-container d-flex p-4">
        <div v-for="(film,index) in dataFilms" :key="index" class="col">
            <CardResult :film="film"/>
        </div>
    </div> 
</template>

<script>
import CardResult from "../components/CardResult.vue"
import axios from "axios";

export default {
    name :"Results",
    props :["testoRicercato"],
    
    components : {
        CardResult,
    },

    data : function (){
        return {
            dataFilms : [],
        }
    },


    mounted () {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=101cc2fb5e4661f4747b2caae74d2081&query="testoRicercato"')
        .then((response) => {

        this.dataFilms = response.data.results
        console.log(this.dataFilms);
    })
  },
  
}
</script>

<style lang="scss" scoped>
.results-container {
    background-color: gray;

}
</style>