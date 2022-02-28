<template>

    <main>

        <FilmList :films='films'/>
        
    </main>
  
</template>

<script>

import FilmList from './FilmList.vue';

export default {
    name:'MyMain',
    props: {
        'films' : Array
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