<template>
  <b-navbar type="is-info">
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
          alt="Lightweight UI components for Vue.js based on Bulma"
        />
      </b-navbar-item>
    </template>
    <template #start> </template>

    <template #end>
      <b-navbar-item tag="div">
        <a style="color: white" class="mr-3"> Admin </a>
        <div class="block">
          <b-icon icon="account" size="is-large" type="is-dark"></b-icon>
          <b-icon icon="view-dashboard" size="is-large" type="is-primary">
          </b-icon>
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
export default {
  name: "NavBar",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
