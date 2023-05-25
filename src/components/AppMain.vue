<script>
    import {store} from '../store';
    import AppCard from './AppCard.vue'
    export default {
        components: {
            AppCard,
        },
        data(){
            return{
            store,
            
            };
        },
    }
</script>


<template>
    <main>
         <div class="movies">
            <div class="movie">Movies</div>
            <AppCard
            v-for="(serie, i) in store.arrMovies"
            :key="i"
            :poster_path="serie.poster_path"
            :title="serie.title"
            :original="serie.original_title"
            :language="serie.original_language"
            :vote="serie.vote_average"
        />
        </div>
        <div class="series">
            <div class="serie">Series</div>
            <AppCard
            v-for="(serie, i) in store.arrSeries"
            :key="i"
            :poster_path="serie.poster_path"
            :title="serie.name"
            :original="serie.original_name"
            :language="serie.original_language"
            :vote="serie.vote_average"
        />
        </div>
        
        <!--<div class="movies">
            <AppCardMovie
            />
        </div>
        <div class="series">
            <AppCardTv/>
        </div>  -->   
        <!-- <div v-for="movie in store.arrMovies" :key="index">
            
        </div>-->
    </main>
</template>



<style lang="scss" scoped>
    .movies{
        display: flex;
        flex-wrap: wrap;
        .movie{
            height: 5rem;
            background-color: black;
            color: white;
            width: 100%;
            justify-content: center;
            display: flex;
            align-items: center;
        }
    }

    .series{
        margin-top: 3rem;
        display: flex;
        flex-wrap: wrap;
        .serie{
            height: 5rem;
            background-color: black;
            color: white;
            width: 100%;
            justify-content: center;
            display: flex;
            align-items: center;
        }
        
    }
        
        
</style>