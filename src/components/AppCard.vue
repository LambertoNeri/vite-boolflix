<script>
    import {store} from '../store'
    import axios from 'axios';
    export default{
        props: {
            poster_path: String,
            title: String,
            original: String,
            language: String,
            vote: Number,
        },

        data(){
            return{
            store,
            };
        },
        methods: {
            languageFilter(data){
                
               /* axios
                
                    .get('https://flagsapi.com/IT/flat/32.png')
                    .then((response) => this.store.flagObject = response)
                return this.store.flagObject  */
                    
                if( data == 'en' ) {
                    return 'https://flagsapi.com/GB/flat/32.png'
                } else if(data == 'ja') {
                    return 'https://flagsapi.com/JP/flat/32.png'

                } else {
                    return 'https://flagsapi.com/'+data.toUpperCase()+'/shiny/32.png'
                }  
            } 
        },
    }   
</script>


<template>
    <div class="card">
        <img v-if="poster_path" :src="`http://image.tmdb.org/t/p/w342${poster_path}`" :alt="poster_path">
        <!-- <img v-else src="../assets/img/fallback-image.png" alt=""> -->
        <span class="title">title: {{ title }}</span>
        <span class="original title">original title: {{ original }}</span>
        <span class="language"><img :src="languageFilter(language)" alt=""></span>
        <span class="vote">vote: {{ vote }}</span>
    </div>
</template>



<style lang="scss" scoped>

    .card{
        display: flex;
        flex-direction: column;
        justify-content: center;
        width: calc(100% / 5);
        border: 1px black solid;
        span{
            text-align: center;
        }
    }

    
</style>