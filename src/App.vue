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
