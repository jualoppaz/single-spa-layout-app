<template>
  <footer class="footer">
    <div class="container">
      <div class="text-center">
        Copyright © 2020
        <a href="http://www.juanmanuellopezpazos.es" target="_blank" id="personal-page-link"
          >Juan Manuel López Pazos</a
        >
        <a
          href="https://github.com/jualoppaz/single-spa-login-example-with-npm-packages"
          target="_blank"
          id="github-link"
        >
          <font-awesome-icon :icon="['fab', 'github']" size="lg" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {},
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

  &:hover {
    color: #42b983;
  }
}

footer {
  background-color: #303846;
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 20px;
  height: 136px;

  @media screen and (min-width:768px){
    height: 77px;
  }

  > div {
    color: #ebedf0;
    line-height: 2;
  }

  a{

    &#github-link {
      margin-left: 10px;
      color: #ebedf0;
      display: block;

      @media screen and (min-width:768px){
        display:inline;
      }
    }

    &#personal-page-link{
      display: block;

      @media screen and (min-width:768px){
        display:inline;
      }
    }
  }
}
</style>
