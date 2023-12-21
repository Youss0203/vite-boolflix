<template lang="">
    <article v-for="film in movies">
        <h1>Title: {{film.title}}</h1>
        <p>Original title: {{film.original_title}}
        </p>
        <p>language: {{ getFlagElement(film.original_language) }}</p>
        <p>overview: {{film.overview}}</p>
        <p>vote: {{film.vote_average}}</p>
    </article>

    
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
article{
    text-align: center;
}
</style>