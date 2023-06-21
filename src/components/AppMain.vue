<template>
    <main>
        <h1>
            I'm the Main
        </h1>
        <h2 class="red">
            Film
        </h2>
        <div v-for="movie in store.movies">
            <h3>
                Originale title:{{ movie.original_title }}
                Film title:{{ movie.title }}
                Lenguage:{{ movie.original_language }}
                Vote:{{ movie.vote_average }}
            </h3>
        </div>
        <h2 class="red">
            Serie
        </h2>
        <div v-for="serie in store.series">
            <h3>
                Originale title:{{ serie.original_name }}
                Film title:{{ serie.name }}
                Lenguage:{{ serie.original_language }}
                Vote:{{ serie.vote_average }}
            </h3>
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
    .red{
        color: red;
    }
</style>