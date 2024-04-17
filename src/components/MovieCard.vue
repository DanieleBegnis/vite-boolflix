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
        <div class="name">[TITOLO]</div>
        <div class="original-name">[TITOLO ORIGINALE]</div>
        <div class="language">[LINGUA]</div>
        <div class="review">[VOTO]</div>
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