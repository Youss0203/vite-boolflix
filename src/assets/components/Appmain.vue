<template lang="">
    <div class="row">
    <div class="container">
    <article v-for="film in movies">
        <h6> {{film.title}}</h6>
        <p>Original title: {{film.original_title}}
        </p>
        <img  :src="'https://image.tmdb.org/t/p/w500' + film.poster_path" alt="film.title">
        <p>language: {{ getFlagElement(film.original_language) }}</p>
        <p>vote: {{film.vote_average}}</p>
    </article>
    </div>
    </div>

    
</template>
<script>
const flags = {
        'it': '🇮🇹',
        'en': '🇬🇧',
        'ja': '🇯🇵',
        'fr': '🇫🇷',
        'de': '🇩🇪',
        'es': '🇪🇸',
     }

export default {
    components:{
       
    },
    data() {
        return {
            lingue: ['en', 'es', 'fr','ja','de','it'],
        }
    },
    props:{
        movies:{
            type:Array,
            required:true,
        },
    },
    methods: {
        getFlagElement(lingue) {
      return flags[lingue] || 'no language specified';
    },
    },
}
</script>
<style lang="scss" scoped>
@use "../../styles/general.scss" as*;
div.container{
    display: flex;
    align-items: stretch;
    flex-wrap: wrap;

    img{
        height: 200px;
    }
}
article{
    text-align: center;
    width: calc((100% / 3) - 1rem);
    margin-left: .5rem;
    margin-right: .5rem;
    color:white;

    p{
        font-size:10px;
    }
}
</style>