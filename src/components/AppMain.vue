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
            <div class="cards">
                <MovieCard  v-for="movie in store.movies" :cardInfo="movie"></MovieCard>
            </div>
            <h2>SERIE TV</h2>
            <div class="cards">
                <TvCard v-for="serie in store.series" :cardInfo="serie"></TvCard>
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
    .cards {
        display: flex;
        flex-wrap: wrap;
    }
    h2{
        text-align: center;
    }
}
</style>