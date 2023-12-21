<template lang="">
    <div class="row">
        <div class="container d-flex justify-content-center">
    <input type="text" placeholder="search a film"  v-model="trovaFilm" class="mt-5">
    <button  @click="$emit('search',trovaFilm)" class="mt-5">search</button>
    </div>
    </div>
</template>
<script>
import {store} from "../../js/store.js";
export default {
    data() {
        return {
            trovaFilm:"",
        }
    },
}
</script>
<style lang="scss" scoped>
@use "../../styles/general.scss" as*;

input{
    border:red 2px solid;
    padding:.5rem 4rem;
}
button{
padding:.5rem 1rem;
border:none; 
background-color: red;
color:white


}button:hover{
    background-color: rgb(234, 38, 38);
}
</style>