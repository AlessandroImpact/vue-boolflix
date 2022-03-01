<template>
  <div id="app">
    <MyHeader @search="doSearch" />
    <MyMain :films="films" :tv="tv" />
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import MyMain from "./components/MyMain.vue";
const axios = require("axios");

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },

  data() {
    return {
      tv: [],
      films: [],
      api_key: "7c9c3d249f254c7408c5f265ee84bd23",
      language: "it_IT",
    };
  },
  methods: {
    doSearch(keyword) {
      const params = {
        params: {
          api_key: this.api_key,
          query: keyword,
          language: this.language,
        },
      };

      this.getFilms(params);
      this.getTv(params);
    },

    getTv(params) {
      let tvRequest = "https://api.themoviedb.org/3/search/tv";

      axios
        .get(tvRequest, params)
        .then((response) => {
          this.tv = response.data.results;
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .then(function () {
          // always executed
        });
    },

    getFilms(params) {
      let filmRequest = "https://api.themoviedb.org/3/search/movie";
      axios
        .get(filmRequest, params)
        .then((response) => {
          this.films = response.data.results;
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .then(function () {
          // always executed
        });
    },
  },
};
</script>

<style lang="scss">
@import "./style/general.scss";
@import "~@fortawesome/fontawesome-free/css/all.css";
</style>
