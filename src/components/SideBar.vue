<template>
  <aside class="side">
    <div class="logo">
      <img src="@/assets/Tellylogo.png" alt="Telly Logo">
    </div>
    <ul class="movie-nav">
      <li class="title"> BROWSE TELLY</li>
      <li @click.prevent >
        <a href="#" @click.prevent="navigate('MoviesTv','Movies&TV')">MOVIES & TV</a>
      </li>
      <li >
        <a href="#" @click.prevent="navigate('PopularMovies','Popular Movies')">POPULAR MOVIES</a>
      </li>
      <li >
        <a href="#" @click.prevent="navigate('PopularTvShows','Popular Tv Shows')" >POPULAR TV SHOWS</a>
      </li>
      <br>
      <li class="title"> CATEGORIES</li>
       <li >
        <a href="#" @click.prevent="navigate('UpComingMovies','Up Coming Movies')">UP COMING MOVIES</a>
      </li>
       <li >
        <a href="#" @click.prevent="navigate('AiringToday','Airing Today')"> TV SHOWS AIRING TODAY</a>
      </li>
    </ul>
  </aside>
</template>

<script>
import { eventBus } from '../main';
export default {
  methods: {
    navigate(neView, title) {
      eventBus.$emit('changeView', {
        tag: neView,
        title: title,
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../sass/colors';

.side {
  background-color: $sidebkg;
  width: 250px;
  height: 100vh;
  font-size: 12px;
  font-weight: 800;
}
ul {
  margin: 0px 20px;
  list-style: outside none none;

  li {
    padding: 10px;
    font: 800 !important;
  }
  a {
    text-decoration: none;
    color: $primary;
    font: to-upper-case($string: '');
  }

  .title {
    font-weight: 200;
    color: $title;
  }

  .active {
    a {
      color: $active;
    }
  }
}
</style>

