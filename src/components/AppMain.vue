<script>
    import {store} from '../store';
    import AppCardMovie from './AppCardMovie.vue';
    export default {
        components: {
            AppCardMovie,
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
        <div class="series"></div>
        <!-- <div v-for="movie in store.arrMovies" :key="index">
            
        </div>-->
    </main>
</template>



<style lang="scss" scoped>
    .movies{
        display: flex;
        flex-wrap: wrap;
        
    }
</style>