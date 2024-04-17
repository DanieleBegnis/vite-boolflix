<script>
export default {
    name: 'MovieCard',
    props: {
        cardInfo: Object
    }
}
</script>

<template>
    <div class="single-card">
        <div class="name">{{ cardInfo.title }}</div>
        <div class="original-name">{{ cardInfo.original_title }}</div>
        <div class="language">{{ cardInfo.original_language }}</div>
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