<template>
  <div id="app">

    <MyHeader @search='getFilms'/>
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

      films: []


    }
  },
  methods: {
      getFilms(keyword) {

    axios.get('https://api.themoviedb.org/3/movie/550?api_key=7c9c3d249f254c7408c5f265ee84bd23&query='+keyword+'')

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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
