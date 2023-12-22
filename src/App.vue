<template lang="">
  <appHeader @search="getFilmAndSeries"/>
  <main>
  <appmain :movies="movieslist"/>
  <appSeries :series="seriesList"/>
  </main>

</template>
<script>
import axios from "axios";
import appHeader from "./assets/components/appHeader.vue"
import Appmain from './assets/components/Appmain.vue';
import appSeries from "./assets/components/appSeries.vue";
export default {
  components: {
    appHeader,
    Appmain,
    appSeries

  },
  data() {
    return {
      movieslist:[],
      seriesList:[],
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
    },
    getSeriesElement(cercaSerie=''){
      console.log(cercaSerie)
      axios.get('https://api.themoviedb.org/3/search/tv?api_key=4f1af5c5fa62d3f92335f2fe43c3b48c&query='+ cercaSerie)
        .then((response) => {
          // handle success
          console.log(response);
          this.seriesList=response.data.results
        })
        .catch(function (error) {
          // handle error
          console.error(error);
        });
    },
    
        getFilmAndSeries(searchedString=""){
            this.getFilmElement(searchedString);
            this.getSeriesElement(searchedString)
        },
    },
  created() {
    console.log("film")
    this.getFilmElement("")
  },
  created() {
    this.getSeriesElement("")
  },
  created() {
    this.getFilmAndSeries("fast")
  },


}
</script>
<style lang="scss">
@use "./styles/general.scss" as*;
</style>
