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
</style>