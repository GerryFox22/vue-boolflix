<template>
    <div class="container-results">
        <div class="results-container d-flex p-4 flex-wrap row-cols-4">
            <div v-for="film in dataFilms" :key="film.id" class="single-result col">
                <CardResult :film="film"/>
            </div>
            <div v-for="film in dataTeleFilms" :key="film.id" class="single-result col">
                <CardResult :film="film"/>
            </div>
        </div>  
    </div>
        
</template>

<script>
import CardResult from "../components/CardResult.vue"
// import axios from "axios";

export default {
    name :"Results",
    props :["dataFilms", "dataTeleFilms"],
    
    components : {
        CardResult,
    },

    data : function (){
        return {

        }
    },

    methods :{
       
    },


    mounted () {
      
  },
  
}
</script>

<style lang="scss" scoped>
.results-container {
    background-color: gray;

}

.single-result {
    background-color: orange;
    border: 5px solid gray;
}
</style>