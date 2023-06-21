<template>
    <div>
        <input type="text" v-model="store.searchBar" @keyup="$emit('research')">
        <button @click="$emit('research')">Search film</button>
    </div>
</template>
<script>
import { store } from '../store';
export default {
    name: 'AppSearchbar',

    data(){
        return{
            store,
        }
    }
}
</script>
<style lang="scss" scoped>
    
</style>