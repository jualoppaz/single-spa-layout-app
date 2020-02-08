<template>
  <div id="header" class="clearfix">
    <b-navbar type="light" variant="light" fixed="top">
      <b-navbar-brand>
        <a href="https://single-spa.js.org" target="_blank">
          <img id="logo" src="../assets/logo.svg" />
          Single spa
        </a>
      </b-navbar-brand>

      <b-navbar-nav class="ml-auto">
        <b-nav-item-dropdown right>
          <template v-slot:button-content>
            <em> {{ username }}</em>
          </template>
          <b-dropdown-item v-on:click="logout">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {},
  methods: {
    logout() {
      sessionStorage.removeItem('user');
      sessionStorage.removeItem('token');
      window.history.pushState(null, null, '/login');
    },
  },
  computed: {
    username() {
      const user = sessionStorage.getItem('user');
      return user ? JSON.parse(user).username : '';
    },
  },
};
</script>

<style lang="scss" scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#header {
  nav.navbar {
    border-bottom: 1px solid #eee;
  }

  img#logo {
    width: 50px;
  }
}
</style>
