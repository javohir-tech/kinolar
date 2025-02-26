<template>
    <div class="shadow mb-5">
        <input v-model="search" @input="searchMovie" type="text" class="form-control p-3" placeholder="Qidiruv">
        <FilterPanel/>
    </div>
</template>
<script>
import FilterPanel from './FilterPanel.vue';

export default {
    components:{
        FilterPanel
    },
    data(){
        return{
            search : ""
        }
    },
    methods:{
        searchMovie(){
           this.$emit('searchMovie', this.search)
        }
    }
}
</script>
<style>
    
</style>