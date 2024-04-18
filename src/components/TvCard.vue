<script>
export default {
    name: 'TvCard',
    props: {
        cardInfo: Object
    },
    data() {
        return {
            maximumVote: 5,
            vote: this.cardInfo.vote_average
        };
    },
    methods: {
    },
    computed: {
        fullStars() {
            return Math.ceil(this.vote / 2);
        },

        emptyStars() {
            return this.maximumVote - this.fullStars;
        }
    }
}
</script>

<template>
    <div class="single-card">
        <div class="card-image">
            <img :src="`https://image.tmdb.org/t/p/w500${cardInfo.backdrop_path}`" alt="">
        </div>
        <div class="card-informations">
            <div class="name">{{ cardInfo.name }}</div>
            <div class="original-name">{{ cardInfo.original_name }}</div>
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
            <div class="card-review">
                <i class="fa-solid fa-star" v-for="star in fullStars"></i>
                <i class="fa-regular fa-star" v-for="star in emptyStars"></i>
            </div>
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
    -webkit-box-shadow: 0px 0px 27px 1px #E50914;
    -moz-box-shadow: 0px 0px 27px 1px #E50914;
    -o-box-shadow: 0px 0px 27px 1px #E50914;
    box-shadow: 0px 0px 27px 1px #E50914;

    div {
        color: #fff;
        margin: 12px 0;
    }

    p {
        margin-bottom: 6px;
    }
}
.card-image {
    img {
        object-fit: cover;
        width: 100%;

    }
}
.overwiew {
    overflow-y: auto;
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

.single-card:hover .card-image {
    display: none;
}
</style>