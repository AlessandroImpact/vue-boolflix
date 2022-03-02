<template>
<section class="d-flex flex-wrap">
<ul>
    <FilmCard v-for="(film,index) in films" :key="'Film'+index" :film='film'/>
    <TvCard v-for="(tv,index) in tv" :key="'Tv'+index" :tv='tv'/>
</ul>
</section>
  
</template>

<script>
import FilmCard from './partial/FilmCard.vue'
import TvCard from './partial/TvCard.vue'

export default {
    name:'FilmList',
    props: {
        'films': Array,
        'tv': Array
    },

    components: {
        FilmCard,
        TvCard
    }

}
</script>

<style>

    
    


ul{
     list-style-type: none;
     
  
}
</style>