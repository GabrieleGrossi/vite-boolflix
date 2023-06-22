<template>
    <div class="flex">
        <h1>
            Boolfix
        </h1>
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
</style>