<template lang="">
    <article v-for="serie in series">
        <h1>Title: {{serie.name}}</h1>
        <p>Original title: {{serie.original_name}}
        </p>
        <p>language: {{ getFlagElement(serie.original_language) }}</p>
        <p>overview: {{serie.overview}}</p>
        <p>vote: {{serie.vote_average}}</p>
    </article>
</template>
<script>
export default {
    props:{
        series:{
            type:Array,
            required:true,

        }
    }
}
</script>
<style lang="scss">
    
</style>