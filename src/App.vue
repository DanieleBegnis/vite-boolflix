<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  components: {
    AppHeader,
    AppMain

  },
  data() {
    return {
      store
      
    };
  },
  methods: {
    getMoviesFromApi() {
      let apiUrl = 'https://api.themoviedb.org/3/search/movie';
      const queryParams = {
        api_key: '479a9729247295c116f0ae2984f62d3b',

      };
      if(store.searchedMovie !== '') {
        queryParams.query = store.searchedMovie;
      }
      axios.get(apiUrl, {
        params: queryParams
      })
      .then((response) => {
        store.movies = response.data.results;
      });
    }

  },
  mounted() {

  }

}
</script>

<template>
  <AppHeader @searchPerformed="getMoviesFromApi"></AppHeader>
  <AppMain></AppMain>
</template>

<style lang="scss">
@use './style/generic';
</style>

