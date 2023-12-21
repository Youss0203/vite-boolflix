<template lang="">
    <article v-for="film in movies">
        {{film.title}}
        {{film.original_title}}
        {{film.original_language}}
        {{film.vote_average}}
    </article>
</template>
<script>
import {store} from "../../js/store.js";
export default {
    components:{
    },
    data() {
        return {
           
        }
    },
    props:{
        movies:{
            type:Array,
            reuired:true,
        }
    },
}
</script>
<style lang="scss" scoped>
@use "../../styles/general.scss" as*;
article{
    text-align: center;
}
</style>