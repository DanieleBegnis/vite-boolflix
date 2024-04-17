<script>
import { store } from '../store.js';
import MovieCard from './MovieCard.vue';

export default {
    name: 'AppMain',
    components: {
        MovieCard
    },
    data() {
        return {
            store
        };
    }
}
</script>

<template>
    <section class="cards-list">
        <div class="container">
            <div class="movie-cards">
                <MovieCard  v-for="movie in store.movies" :cardInfo="movie"></MovieCard>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
.cards-list {
    background-color: gray;
    padding-top: 24px ;
    padding-bottom: 24px;
}
.container {
    width: 85%;
    margin: 0 auto;
    background-color: #fff;
    .movie-cards {
        display: flex;
        flex-wrap: wrap;
    }
}
</style>