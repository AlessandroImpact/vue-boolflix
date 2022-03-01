<template>
<li>
    <div class="film-card">
        <div class="film-card-inner">
            <div class="film-card-front">
           <img v-if="tv.poster_path" :src= "`https://image.tmdb.org/t/p/w342${tv.title}`">  
            </div>
            <div class="film-card-back">
                <p>{{tv.title}}</p>
                <p>{{tv.original_title}} </p>
                <p><span>{{tv.original_language}}</span> <lang-flag :iso="tv.original_language" /> </p>
                <p>{{tv.vote_average}} </p>
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

