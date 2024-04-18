<script>
// import image from ../assets/img/bandiera-GB.png
// import image from '.././assets/img/en.png'
export default {
    name: 'MovieCard',
    props: {
        cardInfo: Object
    },
    methods: {
        // getImageUrl(name) {
        // return new URL(`../assets/img/${name}.png`, import.meta.url).href
        // }
    }
}
</script>

<template>
    <div class="single-card">
        <div class="name">{{ cardInfo.title }}</div>
        <div class="original-name">{{ cardInfo.original_title }}</div>
        <div class="card-flag">
        <div class="language" v-if="cardInfo.original_language === 'en'">
            <!-- <img :src="imgUrl(en)"/> -->
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