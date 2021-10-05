<template>
  <div  class="card-result">
      <div class="film-img">
          <img :src="imgSrc + film.poster_path" alt="">
      </div>
      <div class="film-info">
          <p><strong>Titolo</strong> : 
            <span v-if="film.title">{{film.title}}</span>
            <span v-else>{{film.name}}</span>
          </p>

          <p><strong>Titolo Originale</strong> : 
            <span v-if="film.original_title">{{film.original_title}}</span>
            <span v-else>{{film.original_name}}</span>
          </p>

          <p><strong>Lingua</strong> :
                <img v-if="(film.original_language === 'it')" :src="flags.italy" alt="Italy flag">
                <img v-else-if="(film.original_language === 'en')" :src="flags.england" alt="England flag">
                <img v-else-if="(film.original_language === 'us')" :src="flags.usa" alt="Usa flag">
                <span v-else> {{film.original_language}}</span>
           </p>
          <div class="voto d-flex ">
                <p><strong>Voto</strong> :</p>
                <div v-for="n in mediaVoto(film.vote_average)" :key="n" class="vote-star">
                    <i class="yellow fas fa-star"></i>
                </div>
                <div v-for="n in 5- mediaVoto(film.vote_average)" :key="n" class="vote-star">
                    <i class="fas fa-star"></i>
                </div>
            </div> 

            <p><strong>Overview</strong> : 
                <span v-if="film.original_title">{{film.overview}}</span>
                <span v-else>{{film.original_name}}</span>
            </p>
      </div>
  </div>
</template>

<script>
export default {
    name :"CardResult",
    props : ["film"],
    data : function (){
        return {
            flags : {
                italy :"https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/320px-Flag_of_Italy.svg.png",
                england: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Flag_of_England.svg/1200px-Flag_of_England.svg.png",
                usa : "https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Flag_of_the_United_Kingdom_%283-5%29.svg/1200px-Flag_of_the_United_Kingdom_%283-5%29.svg.png"
            },
            imgSrc :"https://image.tmdb.org/t/p/w342",
            mediaVoti : 0,
        }
    },
    methods :{
        mediaVoto (voto){
            return Math.ceil(voto / 2)
        }
    },
 
}
</script>

<style lang="scss" scoped>


.card-result {
    height: 100%;
    position: relative;

}

ul {
    display: flex;
    list-style: none;
    margin-left: 10px;
    padding: 0;
}

.film-info{
    position: absolute;
    top: 0;
    display: none;
    padding: 20px;
    background-color: black;
    width: 100%;
    height: 100%;
}

.card-result:hover .film-info{
    display: block;

    
}

p {
    color: white;
    img {
        width: 8%;
    }
    i {
        color: yellow;
    }
}

.film-img {
    height: 100%;
    img{  
        width: 100%;
        height: 100%;
    }
}
.yellow{
  color: yellow;
}



</style>