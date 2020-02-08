<template>
  <div id="layout-app">
    <Header />
    <Navbar />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    Header,
    Navbar,
    Footer,
  },
  beforeCreate() {
    if (!sessionStorage.getItem('token')) {
      window.history.pushState(null, null, '/login');
    }
  },
};
</script>

<style lang="scss">
html {
  min-height: 100%;
  position: relative;
}
body {
  height: 100%;
}
</style>
