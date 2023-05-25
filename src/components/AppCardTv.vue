<script>
    import {store} from '../store'
    export default{
    data(){
            return{
            store,
            };
        },
    }
</script>


<template>
    <div class="card" v-for="(serie, index) in store.arrSeries" :key="index">
        <span class="title">title: {{ serie.name }}</span>
        <span class="original title">original title: {{ serie.original_name }}</span>
        <span class="language">language: {{ serie.original_language }}</span>
        <span class="vote">vote: {{ serie.vote_average }}</span>
    </div>
</template>



<style lang="scss" scoped>

    .card{
        border: 1px solid red;
        display: flex;
        flex-direction: column;
        justify-content: center;
        width: calc(100% / 5);
        span{
            text-align: center;
        }
    }
</style>