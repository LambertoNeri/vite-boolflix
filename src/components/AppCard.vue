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
            starArray: [],
            };
        },
        methods: {
            languageFilter(data){
                if( data == 'en' ) {
                    return 'https://flagsapi.com/GB/flat/32.png'
                } else if(data == 'ja') {
                    return 'https://flagsapi.com/JP/flat/32.png'

                } else {
                    return 'https://flagsapi.com/'+data.toUpperCase()+'/shiny/32.png'
                }  
            },
            voteTransformation(data){
                let baseFive;
                baseFive = Math.trunc(data / 2 );
                this.starArray = [];
                return baseFive
                
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
        <div class="star-container">
            voto: 
            <span class="vote" v-for="(star, i) in 5" :key="i">
                
                <font-awesome-icon icon="fa-regular fa-star" v-if="voteTransformation(vote) < i +1 "/>
                <font-awesome-icon icon="fa-solid fa-star" v-else/>
            </span>
        </div>
        
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
        .star-container{
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }

    
</style>