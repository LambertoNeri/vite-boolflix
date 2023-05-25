<script>
    import {store} from '../store'
    export default{
        data(){
            return{
            store,
            };
        },
        methods: {
            languageFilter(index){
                if(index.original_language == 'en' ) {
                    return 'https://flagsapi.com/GB/flat/32.png'
                } else if(index.original_language == 'ja') {
                    return 'https://flagsapi.com/JP/flat/32.png'

                } else {
                    return 'https://flagsapi.com/'+index.original_language.toUpperCase()+'/shiny/32.png'
                }
            } 
        },
    }   
</script>


<template>
    <div class="card" v-for="(serie, index) in store.arrSeries" :key="index">
        <img v-if="serie.poster_path" :src="`http://image.tmdb.org/t/p/w342${serie.poster_path}`" :alt="serie.poster_path">
       <!-- <img v-else src="../assets/img/fallback-image.png" alt=""> -->
        <span class="title">title: {{ serie.name }}</span>
        <span class="original title">original title: {{ serie.original_name }}</span>
        <span class="language"><img :src="languageFilter(serie)" alt=""></span>
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