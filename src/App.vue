<template lang="">
  <appHeader/>
  <appmain/>
</template>
<script>
import axios from "axios";
import {store} from "./js/store.js";
import appHeader from "./assets/components/appHeader.vue"
import Appmain from './assets/components/Appmain.vue';
export default {
  components:{
    appHeader,
    Appmain,

  },
  data() {
    return {
      store,
    }
  },

}
</script>
<style lang="scss">
  @use "./styles/general.scss" as*;
</style>
