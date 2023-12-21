<template lang="">
  <appHeader @search="getFilmElement"/>
  <appmain :movies="movieslist"/>
</template>
<script>
import axios from "axios";
import { store } from "./js/store.js";
import appHeader from "./assets/components/appHeader.vue"
import Appmain from './assets/components/Appmain.vue';
export default {
  components: {
    appHeader,
    Appmain,

  },
  data() {
    return {
      movieslist:[],
    }
  },
  methods: {
    getFilmElement(cercaFilm=''){
      console.log(cercaFilm)
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=4f1af5c5fa62d3f92335f2fe43c3b48c&query='+ cercaFilm)
        .then((response) => {
          // handle success
          console.log(response);
          this.movieslist=response.data.results
        })
        .catch(function (error) {
          // handle error
          console.error(error);
        });
    }
  },
  created() {
    console.log("film")
    this.getFilmElement("007")
  },


}
</script>
<style lang="scss">
@use "./styles/general.scss" as*;
</style>
