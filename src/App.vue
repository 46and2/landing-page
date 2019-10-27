<template>
  <div id="app">
    <top-nav></top-nav>
    <image-slider title="Коттедж «Уют» из дерева"></image-slider>
  </div>
</template>

<script>
import TopNav from './components/TopNav.vue';
import Slider from './components/Slider.vue';

export default {
  name: 'app',
  components: {
    'top-nav': TopNav,
    'image-slider': Slider,
  },
};
</script>

<style>
body {
  margin: 0;
}

#app {
  width: 100%;
  font-family: "MuseoSansCyrl", sans-serif;
}
</style>
