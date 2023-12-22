<template lang="">
    <article v-for="serie in series">
        <h6> {{serie.name}}</h6>
        <p>Original title: {{serie.original_name}}
        </p>
        <img  :src="'https://image.tmdb.org/t/p/w500' + serie.poster_path" alt="film.title">
        <p>language: {{ getFlagElement(serie.original_language) }}</p>
        <p>vote: {{serie.vote_average}}</p>
    </article>
</template>
<script>
export default {
    props:{
        series:{
            type:Array,
            required:true,

        },

}
}
</script>
<style lang="scss">
    
</style>