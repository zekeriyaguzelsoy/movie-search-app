<template>
  <div class="home">
    <input v-model="query" type="text">
    <button @click="search">
      Search
    </button>
    <h1>{{ list.lenght }}</h1>
    <MovieList :list="list" />
  </div>
</template>

<script>
// @ is an alias to /src
import MovieList from '../components/MovieList.vue';

export default {
  name: 'Home',
  components: {
    MovieList,
  },
  data() {
    return {
      query: '',
      list: [],
    };
  },
  methods: {
    search() {
      const movieApi = `http://www.omdbapi.com/?apikey=${process.env.VUE_APP_THMD_API_KEY}&s=${this.query}`;

      fetch(movieApi, { method: 'GET' })
        .then((response) => response.json())
        .then((response) => {
          if (response.error) {
            console.log('Error :>>', Error);
          } else {
            this.list = response.Search;
          }
        });
    },
  },
};
</script>
