<template>
  <div id="app">

    <MyHeader @search="getFilms"/>
    <MyMain :films="films"/>
   
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

const axios = require('axios');

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain 
  },

  data(){
    return {

      films: [],
      api_key:'7c9c3d249f254c7408c5f265ee84bd23',
      language:'it_IT'


    }
  },
  methods: {
      getFilms(keyword) {

    const params = {
      params:{
      'api_key': this.api_key,
      'query': keyword,
      'language': this.language
      }
   };

    axios.get('https://api.themoviedb.org/3/movie/',{ params})

    .then( (response) =>{
      this.films = response.data.results;
    })

    .catch(function (error) {
      // handle error
      console.log(error);
    })
    .then(function () {
      // always executed
    });
      }
  }
}
</script>

<style lang="scss">

@import './style/general.scss'

</style>
