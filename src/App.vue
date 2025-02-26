<template>
  <div class="container">
    <div class="content">
      <AppInfo :allMovies="movies.length" :likedMovies="movies.filter(movie => movie.like === true).length" />
      <SearchPanel />
      <MovieList :movies="movies" @toggleHandle="toggleHandle" @toggle-delete="toggleDelete" />
      <MovieAddForm @add-movie="addNewMovie" />
    </div>
  </div>
</template>
<script>
import AppInfo from './Components/AppInfo.vue';
import MovieAddForm from './Components/MovieAddForm.vue';
import MovieList from './Components/MovieList.vue';
import SearchPanel from './Components/SearchPanel.vue';

export default {
  components: {
    AppInfo,
    SearchPanel,
    MovieList,
    MovieAddForm
  },
  data() {
    return {
      movies: [
        {
          name: "Taxtlar O'yini",
          viewers: 12342,
          favorite: false,
          like: true,
          id: 1
        },
        {
          name: "Titanlar Hujumi",
          viewers: 1232,
          favorite: true,
          like: false,
          id: 2
        },
        {
          name: "Intertellar",
          viewers: 234,
          favorite: false,
          like: true,
          id: 3
        }
      ]
    }
  },
  methods: {
    addNewMovie(newMovie) {
      this.movies.push(newMovie)
    },
    toggleHandle({id, prop}) {
     this.movies = this.movies.map(item =>{
        if(item.id == id){
          return {...item , [prop]: !item[prop]}
        }
        return  item
      })
    },
    toggleDelete(id) {
      this.movies = this.movies.filter(item => item.id !== id)
    }
  }
}
</script>
<style></style>