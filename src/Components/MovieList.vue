<template>
    <div class="mb-5">
        <ul style="list-style: none;">
            <MovieListItems v-for="movie in movies" :key="movie.id" :kino="movie"
                @toggleHandle="$emit('toggleHandle', $event)" @toggle-delete="$emit('toggle-delete' , movie.id)" />
        </ul>
    </div>
</template>
<script>
import MovieListItems from './MovieListItems.vue';

export default {
    components: {
        MovieListItems
    },
    props: {
        movies: {
            type: Array,
            required: true
        }
    }
}
</script>
<style></style>