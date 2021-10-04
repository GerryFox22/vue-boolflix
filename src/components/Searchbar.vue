<template>
  <div class="Searchbar d-flex justify-content-between p-4">
    <div class="logo-container">
        <img src="../assets/netflix-logo.png" alt="Netflix logo">
    </div>
    <div class="search-container">
        <input type="text" placeholder="Cerca" v-model.trim="ricerca" >
        <button   @click="$emit ('search', ricerca )">Cerca</button>
    </div>    
  </div>
</template>

<script>
// import axios from "axios";
export default {
    name :"Searchbar",
    data : function(){
        return {
            ricerca:"",
           
        }
    },
    methods :{
        // searchByName : function () {
            // axios.get("https://api.themoviedb.org/3/search/movie?api_key=101cc2fb5e4661f4747b2caae74d2081&query=" + this.ricerca)
            // .then((response) => {

            // this.dataFilms = response.data.results
          
            // })
            // axios.get("https://api.themoviedb.org/3/search/tv?api_key=101cc2fb5e4661f4747b2caae74d2081&query=" + this.ricerca)
            // .then((response) => {

            // this.dataFilms = response.data.results
          
            // })
        // },
    },
}
</script>

<style lang="scss" scoped>
.Searchbar {
    background-color: black;
}
.logo-container {
    img {
        width: 50%;
    }
}
</style>