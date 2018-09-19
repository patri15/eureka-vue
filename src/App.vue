<template>
  <div id="app">
    <div class="header-top">
      <navbar-top></navbar-top>
      <header-main></header-main>
    </div>
    <navbar-filter></navbar-filter>
    <scroll></scroll>
    <footer-main></footer-main>
  </div>
</template>

<script>

import NavbarTop from './components/NavbarTop.vue';
import HeaderMain from './components/Header.vue';
import NavbarFilter from './components/NavbarFilter.vue';
import FooterMain from './components/Footer.vue';
import Scroll from './components/Scroll.vue';
import InfiniteLoading from 'vue-infinite-loading';

export default {
  name: 'app',
  components: {
    NavbarTop,
    HeaderMain,
    NavbarFilter,
    FooterMain,
    Scroll,
    InfiniteLoading
  }
}
</script>

<style lang="scss">
  .header-top {
    background-image: url("https://www.passionclub.ro/upload/slider/slider-1.jpg");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
</style>
