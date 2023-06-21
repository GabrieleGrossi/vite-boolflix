<template>
  <div>
    <AppHeader/>
    <AppMain/>
  </div>
  
</template>

<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  name: 'App',
  components:{
    AppHeader,
    AppMain
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/partial/_mixinis.scss';
@import './style/partial/_variables.scss';
</style>
