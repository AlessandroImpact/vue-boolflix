<template>
<li>
    <div class="film-card">
        <div class="film-card-inner">
            <div class="film-card-front">
           <img :src="'https://image.tmdb.org/t/p/w342/'+tv.poster_path"> 
            </div>
            <div class="film-card-back">
                <p>{{tv.title}}</p>
                <p>{{tv.original_title}} </p>
                <p><span>{{tv.original_language}}</span> <lang-flag :iso="tv.original_language" /> </p>
                <p>{{tv.vote_average}} </p>
                  <i v-for="i in 5" :key="i" class=" fa-star" :class="(i < getComputedStar) ?'fa-solid':'fa-regular'"></i>
             </div>
        </div>
</div>

</li>
  
</template>

<script>

import LangFlag from '../../../node_modules/vue-lang-code-flags';

export default {
    name: 'TvCard',
    props: {
        'tv': Object
    },
     components: {
    LangFlag,
  },
   computed:{
      getComputedStar(){
          return Math.ceil(this.tv.vote_average /2)
      }
   },

    data() {
        return {

        }

    }

}
</script>

<style lang="scss" scoped>

@import '../../style/general.scss';
@import '../../style/card.scss';

</style>

