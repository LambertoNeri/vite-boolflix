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
    <div class="card" v-for="movie in store.arrMovies" :key="index">
        <span class="title">title: {{ movie.title }}</span>
        <span class="original title">original title: {{ movie.original_title }}</span>
        <span class="language">language: {{ movie.original_language }}</span>
        <span class="vote">language: {{ movie.vote_average }}</span>
    </div>
</template>



<style lang="scss" scoped>

    .card{
        border: 1px solid black;
        display: flex;
        flex-direction: column;
        justify-content: center;
        width: calc(100% / 5);
        span{
            text-align: center;
        }
    }
</style>