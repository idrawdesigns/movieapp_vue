<template>
  <div id="app">
   <side-bar/>
   <app-content/>
  </div>
</template>

<script>
import SideBar from './components/SideBar.vue';
import Content from './components/Content.vue';

export default {
  name: 'app',
  data() {},
  components: {
    SideBar,
    appContent: Content,
  },
};
</script>

<style  lang="scss" >
@import url('https://fonts.googleapis.com/css?family=Muli:400,700,800');
$sidebkg: #232d32;
$maincont: #0a0e0f;
$title: #95878b;
$swatch_3: #dc8873;
$active: #0cd0fc;
$primary: #ecebee;
$secondary: #9eb3c4;
$swatch_7: #dec1b5;
$btncolor: #55e4f5;
$title: #95878b;
$swatch_3: #dc8873;
$active: #0cd0fc;
$primary: #ecebee;
$secondary: #9eb3c4;
$swatch_7: #dec1b5;
$btncolor: #55e4f5;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  font-family: 'Muli', sans-serif;
  font-weight: 400;
  text-rendering: optimizeLegibility;
}

#app {
  display: flex;
}
</style>
