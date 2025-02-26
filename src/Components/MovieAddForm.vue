<template>
    <div>
        <form @submit.prevent="addMovie">
            <div class="d-flex gap-3">
                <input v-model="movieName" type="text" class="form-control" placeholder="Kino Nomi">
                <input v-model.number="movieViewers" type="number" class="form-control" placeholder="Nechi Marta Ko'rilgan ">
            </div>
            <button class="btn btn-success w-100 mt-3" type="submit">Qo'shish</button>
        </form>
    </div>
</template>
<script>
export default {
    data() {
        return {
            movieName: "",
            movieViewers: ""
        }
    },
    methods: {
        addMovie() {
            if (!this.movieName || !this.movieViewers) {
                alert("Iltimos barcha maydonlarni toldiring")
                return
            }

            const newMovie = {
                name: this.movieName,
                viewers: this.movieViewers,
                favorite: false,
                like:false,
                id: Date.now()
            }

            this.$emit("add-movie", newMovie)

            this.movieName = ""
            this.movieViewers = ""
        }
    }
}
</script>
<style></style>