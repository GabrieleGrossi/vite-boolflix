<template>
    <main>
        <div v-for="movie in store.movies">
            <h2>
                Film
            </h2>
            <h3>
                {{ movie.original_title }}
            </h3>
            <h4>
                {{ movie.title }}
            </h4>
            <h4>
                {{ movie.original_lenguage }}
            </h4>
            <h4>
                {{ movie.vote_avarage }}
            </h4>
        </div>
        <div v-for="serie in store.series">
            <h2>
                Serie
            </h2>
            <h3>
                {{ serie.original_name }}
            </h3>
            <h4>
                {{ serie.name }}
            </h4>
            <h4>
                {{ serie.original_lenguage }}
            </h4>
            <h4>
                {{ serie.vote_avarage }}
            </h4>
        </div>
    </main>
</template>
<script>
import { store } from '../store';
export default {
    name: 'AppMain',
    data(){
        return{
            store,
        }
    },
    methods:{

    } 
}
</script>
<style>
    
</style>