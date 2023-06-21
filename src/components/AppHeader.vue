<template>
    <div>
        <h1>
            I'm the Header
        </h1>
        <AppSearchbar/>
    </div>
</template>
<script>
import AppSearchbar from './AppSearchbar.vue';
import { store } from '../store';
export default {
    name: 'AppHeader',
    data(){
        return{
            store
        }
    },
    components:{
        AppSearchbar
    }
}
</script>
<style lang="scss" scoped>
    @use '../style/general.scss';
</style>