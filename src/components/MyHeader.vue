<template>

<header class="d-flex justify-content-between text-white">
    <img class="" src="../assets/logo-netflix-png.png" alt="logo netflix">
    <form class=" d-flex align-items-center">

        <input type="text" v-model="searchText">
        <button type="submit" @click.prevent="$emit('search', searchText)" >Ricerca</button>

    </form>
</header>
  
</template>

<script>
export default {
    name: 'MyHeader',

    data() {
        return {
            searchText : ''
        }
    }


}
</script>

<style lang="scss" scoped>


@import '../style/general.scss';


header{
    height: 100px;
    background-color: black;
}

</style>

