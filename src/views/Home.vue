<template>
  <div class="home">
    <NavBar msg="Welcome to Your Vue.js App" />
    <section class="container mt-6" style="width: 80%">
      <div class="columns is-variable is-8 mt-5">
        <div class="column"><Card title="Manage Vehicle" /></div>
        <div class="column"><Card title="Manage Parts" /></div>
        <div class="column"><Card title="Approving Price" /></div>
      </div>
    </section>
    <section class="container mt-6">
      <div class="columns">
        <div class="column is-half has-text-left mt-6">
          <p class="ml-6">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illum
            nulla fugit in a eveniet voluptate iste optio, accusamus officiis
            non error reprehenderit dolore dolorem cupiditate tenetur
            praesentium? Corrupti, dicta nesciunt sunt deleniti ullam
          </p>
        </div>
        <div class="column is-half">Image</div>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from "@/components/NavBar.vue";
import Card from "@/components/Card.vue";
export default {
  name: "Home",
  components: {
    NavBar,
    Card,
  },
};
</script>

<style scoped>
/* .column {
  background-color: yellow;
}
.container {
  background-color: rgb(27, 112, 27);
} */
</style>