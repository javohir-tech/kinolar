<template>
    <div class="btn-group mt-3">
        <button @click="$emit('filter', 'allMovies')" class="btn"
            :class="{ 'btn-success': selectedFilter === 'allMovies', 'btn-outline-success': selectedFilter !== 'allMovies' }">Barcha
            Kinolar</button>
        <button @click="$emit('filter', 'like')" class="btn btn-outline-success"
        :class="{'btn-success': selectedFilter === 'favorites', 'btn-outline-success': selectedFilter !== 'like'}"
        >Sevimli Kinolar</button>
        <button @click="$emit('filter', 'favorite')" class="btn btn-outline-success"
        :class="{'btn-success': selectedFilter === 'favorites', 'btn-outline-success': selectedFilter !== 'favorite'}"
        >Mashhur Kinolar</button>
    </div>
</template>
<script>
export default {
    props: {
        selectedFilter: String
    }
}
</script>
<style></style>