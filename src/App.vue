<template>
  <div id="layout-app">
    <Topbar />
    <Sidebar />
  </div>
</template>

<script>
import Topbar from "./components/Topbar.vue";
import Sidebar from "./components/Sidebar.vue";

export default {
  name: "app",
  components: {
    Topbar,
    Sidebar
  },
  beforeCreate() {
    if (!sessionStorage.getItem("token")) {
      window.history.pushState(null, null, "/login");
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
