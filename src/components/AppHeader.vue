<template>
    <div class="flex">
        <!--Credits for the Boolflix Logo to Emanuela Pau-->
        <img src="../assets/boolflix_logo.png" alt="Netflix logo">
        <AppSearchbar/>
    </div>
</template>
<script>
import AppSearchbar from './AppSearchbar.vue';
export default {
    name: 'AppHeader',
    data(){
        return{
            
        }
    },
    components:{
        AppSearchbar
    }
}
</script>
<style lang="scss" scoped>
    @use '../style/general.scss';
    div{
        background-color: black;
    }
    img{
        width: 150px;
        margin-left: 1.5rem;
    }
</style>