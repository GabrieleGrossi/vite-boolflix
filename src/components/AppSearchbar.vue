<template>
    <div class="searchbar">
        <i class="fa-solid fa-magnifying-glass icon"></i>
        <input type="text" v-model="researchText" @keyup="searchMovie(researchText)">
        <button @click="searchMovie(researchText), researchText=''">Search film</button>
    </div>
</template>
<script>
import { store } from '../store';
import axios from 'axios';
export default {
    name: 'AppSearchbar',

    data(){
        return{
            store,
            researchText:'',
            apiUrl:'https://api.themoviedb.org/3/search/',
            tokenAcces: 'api_key=0a1985f8ba6f9af085da000d83018b12',
            apiKey: 'eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIwYTE5ODVmOGJhNmY5YWYwODVkYTAwMGQ4MzAxOGIxMiIsInN1YiI6IjY0OTJjMDE4YzI4MjNhMDExY2RiYmQ4ZiIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.rjoTAjJQnTZircyjbvjJMh1rWLsXeA49Rb5O4Ny4A60',
        }
    },
    methods: {
        searchMovie(search){
            axios.get(`${this.apiUrl}movie?${this.tokenAcces}&query=${search}`)
            .then((response)=>{
                this.store.movies=response.data.results;
                console.log(response.data.results)
            })
            axios.get(`${this.apiUrl}tv?${this.tokenAcces}&query=${search}`)
            .then((response)=>{
                this.store.series= response.data.results;
                console.log(response.data.results)
            })
        }
    },
}
</script>
<style lang="scss" scoped>
    .searchbar{
        margin:1.5rem 1.5rem;

    }
    .icon{
        color: white;
        margin-right: 1.5rem;
    }
</style>