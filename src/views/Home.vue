<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Hell msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import Hell from "@/components/Hell.vue";

export default {
  name: "Home",
  components: {
    Hell,
  },
};
</script>
