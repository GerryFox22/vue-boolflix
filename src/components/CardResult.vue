<template>
  <div class="card-result">
      <div class="film info">
          <p><strong>Titolo</strong> : {{film.title}}</p>
          <p><strong>Titolo Originale</strong> : {{film.original_title}}</p>
          <p><strong>Lingua</strong> : {{film.original_language}}</p>
          <p><strong>Voto</strong> : {{film.vote_average}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name :"CardResult",
    props : ["film"],
}
</script>

<style>

</style>