<template>
    <ul class="movie-list list group">
        <MovieListItem 
        v-for="movie in movies" 
        :movie="movie" 
        :key="movie.id" 
        @onToggle="$emit('onToggle', $event)"
        @onRemove="$emit('onRemove', $event)"
        />
    </ul>
</template>
<script>
import MovieListItem from '../movie-list-item/MovieListItem.vue';
export default {
    components: {MovieListItem},
    props: {
        movies: {
            type: Array,
            required: true,
        }, 
    },
}
</script>
<style scoped>
    .movie-list{
        margin-top: 1.5rem;
        padding: 1.5rem;
        background-color: #fcfaf5;
        margin-bottom: 1.5rem;
        border-radius: 4px;
        box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
    }
</style>