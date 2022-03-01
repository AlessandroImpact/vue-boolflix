<template>

    <main>

        <FilmList :films='films' :tv='tv'/>
        
    </main>
  
</template>

<script>

import FilmList from './FilmList.vue';

export default {
    name:'MyMain',
    props: {
        'films': Array,
        'tv': Array
    },
    components : {
        FilmList
    }

}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

main {
    background-color: gray;
    min-height: 1000px;

}
</style>