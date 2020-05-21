<template>
  <div class="movie-list-item">
    <div class="movie-list-year">
      <h4>{{ item.Year }}</h4>
    </div>
    <div class="movie-list-image">
      <img :src="item.Poster" :alt="item.Poster">
    </div>
    <div class="movie-list-title">
      <h4>{{ item.Title }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.movie-list-year{
  position: absolute;
  left: 4px;
  top: 4px;
  background-color:#17a2b8;
  color:#fff;
  width: 50px;
  height: 20px;
  text-align: center;
  h4{
    margin:0;
  }
}
.movie-list-image{
  // border:1px solid #dadada;
  img{
    width:100%;
    height: auto;
  }
}
.movie-list-item{
  position: relative;
  margin-right: 16px;
  max-width: 210px;
  margin-bottom: 20px;
}
.movie-list-title{
  h4{
    margin:0;
    font-size: 14px;
  }
}
</style>
