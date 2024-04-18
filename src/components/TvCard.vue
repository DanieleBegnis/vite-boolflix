<script>
export default {
    name: 'TvCard',
    props: {
        cardInfo: Object
    },
    methods: {

    }
}
</script>

<template>
    <div class="single-card">
        <div class="card-image">
            <img :src="`https://image.tmdb.org/t/p/w342${cardInfo.backdrop_path}`" alt="">
        </div>
        <div class="name">{{ cardInfo.name }}</div>
        <div class="original-name">{{ cardInfo.original_name }}</div>
        <div class="card-flag">
            <div class="language" v-if="cardInfo.original_language === 'en'">
                <img src="../assets/img/en.png">
            </div>
            <div class="language" v-else-if="cardInfo.original_language === 'de'">
                <img src="../assets/img/de.png">
            </div>
            <div class="language" v-else-if="cardInfo.original_language === 'it'">
                <img src="../assets/img/it.png">
            </div>
            <div class="language" v-else-if="cardInfo.original_language === 'fr'">
                <img src="../assets/img/fr.png">
            </div>
            <div class="language" v-else-if="cardInfo.original_language === 'es'">
                <img src="../assets/img/es.png">
            </div>
            <div class="language" v-else-if="cardInfo.original_language === 'ja'">
                <img src="../assets/img/ja.png">
            </div>
            <div class="language" v-else>{{ cardInfo.original_language }}</div>
        </div>
        <div class="review">{{ cardInfo.vote_average }}</div>
    </div>
</template>

<style scoped lang="scss">
    .single-card {
        width: calc((100% / 5) - 30px);
        text-align: center;
        margin: 15px;
        background-color: #d48f38;
        img {
            width: 100%;
        }
        .card-name {
            color: #fff;
            margin: 12px 0;
        }
        p {
            margin-bottom: 6px;
        }
    }

</style>