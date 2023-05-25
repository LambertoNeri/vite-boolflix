<script>
import {store} from '../store'

export default {
    data(){
        return{
            store,
        };
    },

    methods: {
        emitFunc() {
            this.$emit('visualizeInputText');
        },
    },
}

    

</script>


<template>
<header>
    <h1>BOOLFIX</h1>
    <div>
        <input type="text" v-model="store.queryText">
        <button @click="emitFunc">
            vai!
        </button>
    </div>
</header>
</template>



<style lang="scss" scoped>
    header{
        height: 10vh;
        background-color: black;
        display: flex;
        justify-content: space-between;
        padding-inline: 2rem;
        align-items: center;
        h1{
            color: red;
            font-size: 2rem;
        }
        input{
            padding-top: 0.5rem;
            padding-bottom: 0.5rem;
            font-size: 1.2rem;
            padding-left: 1rem;
        }
        button{
            padding-top: 0.5rem;
            padding-bottom: 0.5rem;
            font-size: 1.2rem;
            padding-inline: 0.5rem;
            margin-left: 0.5rem;
            background-color: red;
            color: white;
            border: none;
     
        }

    }
</style>