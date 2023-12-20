<template lang="">
    <div class="row">
        <div class="container d-flex justify-content-center">
    <input type="text" placeholder="search a film" class="mt-5">
    <button class="mt-5">search</button>
    </div>
    </div>
</template>
<script>
export default {
    
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
}
</style>