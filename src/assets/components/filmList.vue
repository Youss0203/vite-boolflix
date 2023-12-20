<template lang="">
    <film/>
</template>
<script>
import {store} from "../../js/store.js";
import film from './film.vue';
export default {
    components:{
        film,
    },
    data() {
        return {
            store,
        }
    },
}
</script>
<style lang="scss" scoped>
@use "../../styles/general.scss" as*;
</style>