<template>
  <div class="Searchbar d-flex justify-content-between p-4">
    <div class="logo-container">
        <img src="../assets/netflix-logo.png" alt="Netflix logo">
    </div>
    <div class="search-container">
        <input type="text" placeholder="Cerca" v-model.trim="ricerca" @keyup.enter.prevent="$emit ('search', ricerca)">
        <button type="submit" @click.prevent="$emit ('search', ricerca)">Cerca</button>
    </div>    
  </div>
</template>

<script>

export default {
    name :"Searchbar",
    data : function(){
        return {
            ricerca:"",
        }
    },
    methods :{
        
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