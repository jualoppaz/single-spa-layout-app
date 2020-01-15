<template>
  <div id="topbar">
    <b-navbar toggleable="false" type="light" variant="light">
      <!--<b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>-->

      <b-navbar-brand>
        <a href="https://single-spa.js.org" target="_blank">
          <img id="logo" src="../assets/logo.svg" />
        </a>
        Single spa
      </b-navbar-brand>

      <!--<b-collapse id="nav-text-collapse" is-nav>-->
      <b-navbar-nav>
        <b-nav-text>Login example with NPM packages</b-nav-text>
      </b-navbar-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template v-slot:button-content>
            <em> {{ username }}</em>
          </template>
          <b-dropdown-item v-on:click="logout">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
      <!--</b-collapse>-->
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Topbar",
  props: {},
  methods: {
    logout() {
      sessionStorage.removeItem("user");
      sessionStorage.removeItem("token");
      window.history.pushState(null, null, "/login");
    }
  },
  computed: {
    username() {
      const user = sessionStorage.getItem("user");
      return user ? JSON.parse(user).username : "";
    }
  }
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
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#topbar {
  border-bottom: 1px solid #eee;

  img#logo {
    width: 50px;
  }
}
</style>
