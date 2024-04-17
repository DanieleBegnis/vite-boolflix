<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <div class="container">
            <h1>BOOLFLIX</h1>
            <div class="searchbar">
                <button>Cerca</button>
                <input type="text" placeholder="Cerca il film">
            </div>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use '../style/generic';
    header {
        background-color: #000;
        .container {
            width: 85%;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
        }
        h1 {
            color: red;
            padding-top: 6px;
            padding-bottom: 6px;
        }
        .searchbar {
            padding-top: 6px;
            padding-bottom: 6px;
            text-align: center;
        }
    }
</style>