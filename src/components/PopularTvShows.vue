<template>
  <div class="content-list">

    <section v-if="errored">
        <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
  </section>


  <section v-else class='list'>
    <div v-if='loading'>Loading......</div>
    <div
      v-else
      v-for='show in populartv'
      class="list-item"
      >
      <p>{{show.name}}</p>
        
    </div>

  </section>
  

  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'PopularTvShows',
  data() {
    return {
      populartv: null,
      loading: true,
      errored: false
    };
  },
  mounted() {
    axios
      .get(
        'https://api.themoviedb.org/3/tv/popular?api_key=d3a3a6522610a89e5a84e2bf688a170b&language=en-US&page=1'
      )
      .then(res => {
        this.populartv = res.data.results;
        console.log(res.data.results);
      })
      .catch(error => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>
