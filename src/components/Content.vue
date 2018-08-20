<template>
<div class="main-content">
  <div class="inner-wrap">
        <div class="header">
            <div class="nav">
              <a href="#">
               <i class="fas fa-chevron-left arrow"></i>
              </a>
              <a href="#">
                <i class="fas fa-chevron-right arrow"></i>
              </a>
            </div>
            <div class="search">
              <i class="fas fa-search arrow" ></i>
            </div>
            </div>

            <div class="content-wrapper">
              <keep-alive>
                <component :is='currentView.tag'/>
                </keep-alive>
            </div>
        </div>
        </div>
</template>

<script>
import TvMovies from '@/components/TvMovies.vue';
import PopularMovies from '@/components/PopularMovies.vue';
import PopularTvShows from '@/components/PopularTvShows.vue';
import AiringToday from '@/components/AiringToday.vue';
import UpComingMovies from '@/components/UpComingMovies.vue';
import { eventBus } from '../main.js';

export default {
  components: {
    TvMovies,
    PopularMovies,
    PopularTvShows,
    AiringToday,
    UpComingMovies
  },
  created() {
    eventBus.$on('changeView', data => {
      let temp = [
        {
          tag: data.tag,
          title: data.title
        }
      ];
      this.history = temp.concat(this.history.splice(0));
    });
  },
  data() {
    return {
      history: [
        {
          tag: 'TvMovies',
          title: 'Movies & Tv'
        },
        {
          tag: 'PopularMovies',
          title: 'Popular Movies'
        },
        {
          tag: 'PopularTvShows',
          title: 'Popular Tv Shows'
        },
        {
          tag: 'AiringToday',
          title: 'Airing Today'
        },
        {
          tag: 'UpComingMovies',
          title: 'Up Coming Movies'
        }
      ]
    };
  },

  computed: {
    currentView() {
      return this.history[0];
    }
  }
};
</script>

<style lang="scss">
@import '../sass/colors';

.main-content {
  background-color: $main;
  height: 100vh;
  font-size: 12px;
  font-weight: 800;
  flex: 2;
  padding: 50px;
}

.inner-wrap {
  margin-right: 50px;

  a {
    padding: 10px;
  }

  .arrow {
    color: $primary;
    opacity: 0.6;
  }
  .arrow:hover {
    color: $primary;
    opacity: 0.2;
  }

  .header {
    display: flex;
    justify-content: space-between;
  }
}

.content-wrapper {
  padding-top: 80px;
  display: grid;
  grid-auto-rows: 1fr 1fr;
  grid-row-gap: 250px;
  display: flex;
}

.list {
  display: flex;
}

.list-item {
  width: 150px;
  color: white;
  background-color: #232d32;
  padding: 10px;
  margin: 5px;
}
</style>
