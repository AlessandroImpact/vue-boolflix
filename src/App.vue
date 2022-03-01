<template>
  <div id="app">

    <MyHeader @search="doSearch"/>
    <MyMain :films="films" :tv="tv"/>
   
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'



export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain 
  },

  data(){
    return {
      tv:[],
      films: [],
      api_key:'7c9c3d249f254c7408c5f265ee84bd23',
      language:'it_IT'
    }
  },
  methods: {

    doSearch(keyword) {
      this.getFilms(keyword);
      this.getTv(keyword);
    },


    getTv(keyword){
      

    const axios = require('axios');

     let tvRequest = 'https://api.themoviedb.org/3/search/tv?api_key='+ this.api_key + '&query=" ' + keyword + '"&language=' + this.language + ' ';
   
    axios.get(tvRequest)
    .then( (tvRequest) =>{
      this.tv = tvRequest.data.results;
    })
    .catch(function (error) {
      // handle error
      console.log(error);
    })
    .then(function () {
      // always executed
    });

    },
      
      getFilms(keyword) {

    const axios = require('axios');

     let filmRequest = 'https://api.themoviedb.org/3/search/movie?api_key='+ this.api_key + '&query=" ' + keyword + '"&language=' + this.language + ' ';
   
    axios.get(filmRequest)
    .then( (filmRequest) =>{
      this.films = filmRequest.data.results;
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

@import './style/general.scss';

</style>
