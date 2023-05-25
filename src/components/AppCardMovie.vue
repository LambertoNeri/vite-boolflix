<script>
    import {store} from '../store'
    export default{
        data(){
            return{
            store,
            };
        },
        methods: {
            languageFilter(movie){
                if(movie.original_language == 'en' ) {
                    return 'https://flagsapi.com/GB/flat/32.png'
                } else if(movie.original_language == 'ja') {
                    return 'https://flagsapi.com/JP/flat/32.png'

                } else {
                    return 'https://flagsapi.com/'+movie.original_language.toUpperCase()+'/shiny/32.png'
                }
            }
        }
    }

  
</script>


<template>
    <div class="card" v-for="(movie, index) in store.arrMovies" :key="index">
        <img v-if="movie.poster_path" :src="`http://image.tmdb.org/t/p/w342${movie.poster_path}`" :alt="movie.poster_path">
        <span class="title">title: {{ movie.title }}</span>
        <span class="original title">original title: {{ movie.original_title }}</span>
        <span class="language"><img :src="languageFilter(movie)" alt=""></span>
        <span class="vote">vote: {{ movie.vote_average }}</span>
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