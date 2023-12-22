<template lang="">
    <header>
    <div class="row">
        <div class="container">
        <div class="nav d-flex justify-content-between align-items-center">
            <img src="../../assets/img/logo.jpeg" alt="">
      <div>
    <input type="text" placeholder="search a film"  v-model="trovaFilm"  class="">
    <button  @click="$emit('search',trovaFilm,trovaSerie)" class="">search</button>
        </div>
    </div>
</div>
    </div>
</header>
</template>
<script>
import {store} from "../../js/store.js";
import appSeries from "./appSeries.vue";
export default {
    components:{
        appSeries
    },
    data() {
        return {
            trovaFilm:"",
            trovaSerie:"",
        }
    },
    methods: {
        
    },
}
</script>
<style lang="scss" scoped>
@use "../../styles/general.scss" as*;
header{
    background-color: #101010;
}
input{
    border:red 2px solid;
    padding:.5rem 4rem;
}
button{
padding:.64rem 1rem;
border:none; 
background-color: red;
color:white


}button:hover{
    background-color: rgb(234, 38, 38);
}

img{
    height: 100px;
}
</style>