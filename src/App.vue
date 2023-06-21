<template>
  <div>
    <AppHeader
    @research="movieList()"/>
    <AppMain/>
    <AppFooter/>
  </div>
  
</template>

<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import axios from 'axios';
import { store } from './store';

export default{
  name: 'App',
  components:{
    AppHeader,
    AppMain,
    AppFooter,
  },
  data(){
    return{
      store
    }
  },
  methods:{
    movieList(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=0a1985f8ba6f9af085da000d83018b12&query=' + store.searchBar)
      .then(function (response) {
        console.log(response.data);
        store.apiCall = response.data;
      })
      .catch(function (error) {
        console.log(error);
      })
    }
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/partial/_mixinis.scss';
@import './style/partial/_variables.scss';
</style>
