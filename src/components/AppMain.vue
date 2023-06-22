<template>
    <main>
        <section>
            <h2 class="red">
                Film
            </h2>
            <div class="flex wrap">
                <div v-for="movie in store.movies" class="card relative">
                    <img :src="posterImg(movie.poster_path)" alt="Movie Poster">
                    <div class="absolute">
                        <h3>
                            Originale title:{{ movie.original_title }}
                        </h3>
                        <h3>
                            Film title:{{ movie.title }}
                        </h3>
                        <div v-if="languageImage.includes(movie.original_language + '.jpg')" class="flag">
                            <img :src="getImageLanguage(movie.original_language + '.jpg')" alt="country flag">
                        </div>
                        <div v-else>
                            {{ movie.original_language }}
                        </div>


                        <span class="star"><i class="fa-solid fa-star" v-for="star in Math.ceil(movie.vote_average / 2)"/>
                        </span>
                        <span class="empty-star"><i class="fa-solid fa-star" v-for="emptyStar in 5 - (Math.ceil(movie.vote_average / 2))"/>
                        </span>
                    </div>


                </div>
            </div>
        </section>
        <section>
            <h2 class="red">
                Serie
            </h2>
            <div class="flex wrap">
                <div v-for="serie in store.series" class="card relative">
                    <img :src="posterImg(serie.poster_path)" alt="Series Poster">
                    <div class="absolute">
                        <h3>
                            Originale title:{{ serie.original_name }}                        
                        </h3>
                        <h3>
                            Film title:{{ serie.name }}
                        </h3>
                        <div v-if="languageImage.includes(serie.original_language + '.jpg')" class="flag">
                            <img :src="getImageLanguage(serie.original_language + '.jpg')" alt="country flag">
                        </div>
                        <div v-else>
                            {{ serie.original_language }}
                        </div>
                        <span class="star"><i class="fa-solid fa-star" v-for="star in Math.ceil(serie.vote_average / 2)" /></span>
                        <span class="empty-star"><i class="fa-solid fa-star" v-for="emptyStar in 5 - (Math.ceil(serie.vote_average / 2))" /></span>
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>
<script>
import { store } from '../store';
export default {
    name: 'AppMain',
    data(){
        return{
            store,
            languageImage: [
                "it.jpg",
                "en.jpg",
                "ja.jpg",
                "fr.jpg",
                "de.jpg",
                "es.jpg",
                "ko.jpg",
                "ru.jpg"
            ],
        }
    },
    methods:{
        getImageLanguage: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },     
        posterImg(link){
            let posterLink = 'https://image.tmdb.org/t/p/w500/'
            if(link === null){
                posterLink = 'https://www.tgv.com.my/assets/images/404/movie-poster.jpg'
            }else{
                posterLink += link
            }
            return posterLink
        }
    },
}
</script>
<style>
    main{
        background-color: #2b2a33;
        min-height: 85vh;
    }
    section{
        width: 85%;
        min-height: 500px;
        background-color: pink;
        margin: 0 auto;
        padding-top: 2rem;
        padding-bottom: 2rem;
    }
    img{
        width: 100%;
        height: 100%;
    }
</style>