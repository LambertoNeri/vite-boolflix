<script>
    import {store} from '../store';
    import AppCardMovie from './AppCardMovie.vue';
    import AppCardTv from './AppCardTv.vue';
    export default {
        components: {
            AppCardMovie,
            AppCardTv,
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
            <AppCardMovie/>
        </div>
        <div class="series">
            <AppCardTv/>
        </div>
        <!-- <div v-for="movie in store.arrMovies" :key="index">
            
        </div>-->
    </main>
</template>



<style lang="scss" scoped>
    .movies{
        display: flex;
        flex-wrap: wrap;
    }

    .movies{
        margin-top: 3rem;
        display: flex;
        flex-wrap: wrap;
        
    }
        
</style>