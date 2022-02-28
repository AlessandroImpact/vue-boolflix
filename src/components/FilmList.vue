<template>
<section>
<ul>
    <FilmCard v-for="(film,index) in films" :key="index" :film='film'/>
</ul>
</section>
  
</template>

<script>
import FilmCard from './partial/FilmCard.vue'

export default {
    name:'FilmList',
    props: {
        'films': Array
    },

    components: {
        FilmCard
    }

}
</script>

<style>

</style>