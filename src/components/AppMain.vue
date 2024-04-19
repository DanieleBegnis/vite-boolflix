<script>
import { store } from '../store.js';
import MovieCard from './MovieCard.vue';
import TvCard from './TvCard.vue';

export default {
    name: 'AppMain',
    components: {
        MovieCard,
        TvCard
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
            <h2>FILM</h2>
            <div class="cards">
                <div class="error-message" v-if="store.searchedMovie === ''"> oh oh, devi ancora cercare un film :(</div>
                <MovieCard v-else v-for="movie in store.movies" :cardInfo="movie"></MovieCard>
            </div>
            <h2>SERIE TV</h2>
            <div class="cards">
                <div class="error-message" v-if="store.searchedMovie === ''"> oh oh, devi ancora cercare una serie TV :(</div>
                <TvCard v-else v-for="serie in store.series" :cardInfo="serie"></TvCard>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
.cards-list {
    background-color: gray;
}
h2 {
    padding-top: 24px;
    padding-bottom: 24px;
    color: red;
}
.container {
    width: 85%;
    min-height: calc(100vh - 50px);
    margin: 0 auto;
    background-color: gray;
    .cards {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        .error-message {
            font-weight: 600;
            font-size: 20px;
        }

    }
    h2{
        text-align: center;
    }
}
</style>