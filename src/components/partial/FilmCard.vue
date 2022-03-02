<template>
<li>
    <div class="film-card">
        <div class="film-card-inner">
            <div class="film-card-front">
            <img :src="'https://image.tmdb.org/t/p/w342/'+film.poster_path">
            </div>
            <div class="film-card-back">
                <p>{{film.title}}</p>
                <p>{{film.original_title}} </p>
                <p><span>{{film.original_language}}</span> <lang-flag :iso="film.original_language" /> </p>
                <p>{{film.vote_average}} </p>
                <!--ciclo per far uscire stelle piene o vuote in base al voto in 5i-->
                <i v-for="i in 5" :key="i" class=" fa-star" :class="(i < getComputedStar) ?'fa-solid':'fa-regular'"></i>
               
             </div>
        </div>
</div>

</li>
  
</template>

<script>

import LangFlag from '../../../node_modules/vue-lang-code-flags';

export default {
    name: 'FilmCard',
    props: {
        'film': Object
    },
     components: {
    LangFlag,
  },
  computed:{
      getComputedStar(){
          return Math.ceil(this.film.vote_average /2)
      }
  },
  


}
</script>

<style lang="scss" scoped>

@import '../../style/general.scss';
@import '../../style/card.scss';

</style>

