<template>
    <div>
        <li class="mb-3" :class="[kino.favorite ? 'text-warning' : '']">
            <div class="d-flex align-items-center justify-content-between">
                <div>
                    <h4>{{ kino.name }}</h4>
                </div>
                <div class="d-flex align-itmes-center gap-5">
                    <h4 class="mb-0">{{ kino.viewers }}</h4>
                    <div class="list-icons d-flex gap-3">
                        <button @click="$emit('toggle-favorite', kino)" class="btn border-0">
                            <i class="px-3 py-1 text-warning rounded bi bi-film"></i>
                        </button>
                        <i class="px-3 py-1 text-danger rounded bi bi-trash-fill"></i>
                        <i class="px-3 py-1 text-warning rounded bi bi-star"></i>
                    </div>
                </div>
            </div>
        </li>
    </div>
</template>
<script>
export default {
    props: {
        kino: {
            type: Object,
            required: true
        }
    }
}
</script>
<style scoped>
.list-icons i {
    background-color: #F1F0E9;
}
</style>