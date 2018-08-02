<template>
  <aside class="side">
    <div class="logo">
      <img src="@/assets/Tellylogo.png" alt="Telly Logo">
    </div>
    <ul class="movie-nav">
      <li class="title"> BROWSE TELLY</li>
      <li class="active">
        <a href="#">MOVIES & TV</a>
      </li>
      <li >
        <a href="#">POPULAR MOVIES</a>
      </li>
      <li >
        <a href="#">POPULAR TV SHOWS</a>
      </li>
      <br>
      <li class="title"> CATEGORIES</li>
       <li >
        <a href="#">UP COMING MOVIES</a>
      </li>
       <li >
        <a href="#"> TV SHOWS AIRING TODAY</a>
      </li>
    </ul>
  </aside>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
$sidebkg: #232d32;
$title: #95878b;
$swatch_3: #dc8873;
$active: #0cd0fc;
$primary: #ecebee;
$secondary: #9eb3c4;
$swatch_7: #dec1b5;
$btncolor: #55e4f5;

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

