<template>
  <div id="sidebar">
    <b-nav vertical class="bg-light">
      <b-nav-item href="/angular" v-on:click.prevent="navigateTo('/angular')"
        >Angular</b-nav-item
      >
      <b-nav-item href="/vue" v-on:click.prevent="navigateTo('/vue')"
        >Vue</b-nav-item
      >
    </b-nav>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {},
  methods: {
    navigateTo(url) {
      window.history.pushState(null, null, url);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
  width: 150px;

  &.nav {
    position: fixed;
    height: 100%;
  }
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#sidebar ul {
  border-right: 1px solid #eee;
  padding-top: 76px;
}
</style>
