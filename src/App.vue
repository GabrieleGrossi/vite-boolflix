<template>
  <div>
    <AppHeader/>
    <AppMain/>
  </div>
  
</template>

<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';

export default{
  name: 'App',
  components:{
    AppHeader,
    AppMain,
  },
  data(){
    return{
      store
    }
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/partial/_mixinis.scss';
@import './style/partial/_variables.scss';
</style>
