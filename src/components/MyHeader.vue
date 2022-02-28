<template>

<header>
    <form>

        <input type="text" v-model="searchText">
        <button type="submit">Ricerca</button>

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

</style>

