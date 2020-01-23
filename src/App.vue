<template>
  <div id="layout-app">
    <Topbar />
    <Sidebar />
    <Footer />
  </div>
</template>

<script>
import Topbar from './components/Topbar.vue';
import Sidebar from './components/Sidebar.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    Topbar,
    Sidebar,
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
  margin-bottom: 150px !important;
}

div#layout-app + div[id*="-app"] {
  padding-top: 77px;
}
</style>
