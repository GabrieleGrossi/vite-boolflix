<template>
    <div>
        <section>
            <h2>
                Serie
            </h2>
            <div class="flex wrap">
                <div v-for="serie in store.series" class="card relative hover">
                    <img :src="posterImg(serie.poster_path)" alt="Series Poster" class="poster">
                    <div class="cardinfo">
                        <h3>
                            Originale title:
                            <br>{{ serie.original_name }}                     
                        </h3>
                        <h3>
                            Film title: 
                            <br>{{ serie.name }}
                        </h3>
                        <div v-if="languageImage.includes(serie.original_language + '.jpg')">
                            <span>Original language : </span>
                            <img :src="getImageLanguage(serie.original_language + '.jpg')" alt="country flag" class="flag">
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
    </div>
</template>
<script>
import { store } from '../store';
export default {
    name: 'AppCardSerie',
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
        },
    },
}
</script>
<style lang="scss" scoped>
@use '../style/general.scss';
section{
        width: 85%;
        min-height: 500px;
        color: white;
        margin: 0 auto;
        padding-top: 2rem;
        padding-bottom: 2rem;
    }
    .poster{
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: all 1s ease-in;
    }
    .card{
    width: calc(100% / 5 - 2rem);
    margin: 0.4rem;
    background-color: #2b2a33;
    color: white;
    position: relative;
        div.cardInfo{
            display: block;
            opacity: 0;
        }
        .flag{
            width: 25px;
            height: 15px;
        }
    }
    .card:hover{
        div.cardInfo{
            opacity: 1;
        }
        .poster{
            height: 45%
        }
    }
</style>