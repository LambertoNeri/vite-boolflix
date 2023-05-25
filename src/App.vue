<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import {store} from './store';  



export default {
  data(){
    return{
      store,
    };
  },

  components: {
    AppHeader,
    AppMain,   
  },

  methods: {
   /* changeQueryText(valueFromEmit) {
      
      
      this.requestFilteredMovies()
      console.log('questo è store movie', store.arrMovies)
    }, */
    requestFilteredMovies(){
      axios
        .get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'e99307154c6dfb0b4750f6603256716d',
          query:  this.store.queryText,
        },
      })

      .then((response) => (this.store.arrMovies = response.data.results))        
    }

  },

   
 

}
</script>

<template>
  <AppHeader @visualizeInputText="requestFilteredMovies"/>
  <AppMain/>

</template>

<style lang="scss">
  @use '../src/assets/styles/general.scss' as *;
</style>

<!--'https://api.themoviedb.org/3/search/movie?'-->
