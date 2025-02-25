<template>
  <div class="container">
    <div class="content">
      <AppInfo/>
      <SearchPanel/>
      <MovieList :movies="movies"/>
      <MovieAddForm/>
    </div>
  </div>
</template>
<script>
import AppInfo from './Components/AppInfo.vue';
import MovieAddForm from './Components/MovieAddForm.vue';
import MovieList from './Components/MovieList.vue';
import SearchPanel from './Components/SearchPanel.vue';

export default {
  components:{
    AppInfo,
    SearchPanel,
    MovieList,
    MovieAddForm
  },
  data(){
    return {
      movies:[
        {
          name:"Taxtlar O'yini",
          viewers: 12342,
          favorite: false,
          like:true
        },
        {
          name:"Titanlar Hujumi",
          viewers: 1232,
          favorite: true,
          like:false
        }
      ]
    }
  },
  methods:{
  }
}
</script>
<style>
  
</style>