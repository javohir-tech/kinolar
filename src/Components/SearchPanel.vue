<template>
    <div class="shadow mb-5">
        <input v-model="search" @input="searchMovie" type="text" class="form-control p-3" placeholder="Qidiruv">
        <FilterPanel @filter="filterMovies" :selectedFilter="selectedFilter"/>
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
        },
        filterMovies(filterType){
            this.$emit('filterMovies', filterType)
        }
    },
    props:{
        selectedFilter : String
    }
}
</script>
<style>
    
</style>