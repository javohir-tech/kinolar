<template>
    <div class="mb-5">
        <ul style="list-style: none;" v-if="movies.length > 0">
            <MovieListItems v-for="movie in movies" :key="movie.id" :kino="movie"
                @toggleHandle="$emit('toggleHandle', $event)" @toggle-delete="$emit('toggle-delete', movie.id)" />
        </ul>
        <div v-else>
            <h1 class="text-center">
                <i class="bi bi-cloud-slash-fill"></i>
                <p>Kinolar Yo'q</p>
            </h1>
        </div>
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