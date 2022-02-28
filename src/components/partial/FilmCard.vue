<template>
<li>
    <div class="film-card">
        <div class="film-card-inner">
            <div class="film-card-front">
            <!--<img src="" alt="" style="width:300px;height:300px;">  qui va l'immagine del titolo--> 
            </div>
            <div class="film-card-back">
                <p>{{film.title}}</p>
                <p>{{film.original_title}} </p>
                <p><span>{{film.original_language}}</span> <lang-flag :iso="movies.original_language" /> </p>
                <p>{{film.vote_average}} </p>
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

}
</script>

<style lang="scss" scoped>

@import '../../style/general.scss';
@import '../../style/card.scss';

</style>

