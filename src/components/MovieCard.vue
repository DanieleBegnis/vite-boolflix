<script>

export default {
    name: 'MovieCard',
    props: {
        cardInfo: Object
    },
    methods: {
        roundVote() {
            console.log(roundVote)
            Math.ceil(cardInfo.vote_average)
            
        }
    }
}
</script>

<template>
    <div class="single-card">
        <div class="card-image">
            <img :src="`https://image.tmdb.org/t/p/w342${cardInfo.backdrop_path}`" alt="">
        </div>
        <div class="card-informations">
            <div class="name">{{ cardInfo.title }}</div>
            <div class="original-name">{{ cardInfo.original_title }}</div>
            <div class="card-flag">
                <div class="language" v-if="cardInfo.original_language === 'en'">
                    <img class="language-img" src="../assets/img/en.png">
                </div>
                <div class="language" v-else-if="cardInfo.original_language === 'de'">
                    <img class="language-img" src="../assets/img/de.png">
                </div>
                <div class="language" v-else-if="cardInfo.original_language === 'it'">
                    <img class="language-img" src="../assets/img/it.png">
                </div>
                <div class="language" v-else-if="cardInfo.original_language === 'fr'">
                    <img class="language-img" src="../assets/img/fr.png">
                </div>
                <div class="language" v-else-if="cardInfo.original_language === 'es'">
                    <img class="language-img" src="../assets/img/es.png">
                </div>
                <div class="language" v-else-if="cardInfo.original_language === 'ja'">
                    <img class="language-img" src="../assets/img/ja.png">
                </div>
                <div class="language" v-else>{{ cardInfo.original_language }}</div>
            </div>
            <!-- <div class="review">{{ roundVote() }}</div> -->
            <div class="overwiew">{{ cardInfo.overview }}</div>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .single-card {
        width: calc((100% / 3) - 30px);
        text-align: center;
        margin: 15px;
        background-color: #000;
        border: 3px solid lightgray;
        div {
            color: #fff;
            margin: 12px 0;
        }
        p {
            margin-bottom: 6px;
        }
    }
    .language-img {
        width: 16px;
    }
    .card-informations {
        display: none;
    }
    .single-card:hover .card-informations {
        display: block;
    }

</style>