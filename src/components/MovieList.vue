<template>
  <div class="movie-list-box">
    <MovieListItem v-for="item in list" :key="item.imdbID" :item="item" />
  </div>
</template>

<script>
import MovieListItem from './MovieListItem.vue';

export default {
  components: {
    MovieListItem,
  },
  props: {
    list: {
      type: Array,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.movie-list-box{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: start;
  max-width: 1200px;
  width:100%;
  margin:0 auto;
}
</style>
