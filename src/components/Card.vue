<template>
  <div class="card grad has-text-light m-5 rounded">
    <header class="">
      <p class="card-header-title"></p>
    </header>
    <div class="card-content mt-3">
      <h4 class="title is-centered has-text-weight-bold has-text-light">
        {{ title }}
      </h4>
      <div class="content is-size-7 has-text-centered">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec
        iaculis mauris. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        Phasellus nec iaculis mauris.
      </div>

      <div class="is-primary has-text-weight-bold">
        <b-button
          rounded
          type="is-info extend"
          class="has-text-weight-bold mt-5"
          inverted
          >GO</b-button
        >
      </div>
    </div>
    <footer class="">
      <a href="#" class="card-footer-item"></a>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: String,
  },
};
</script>

<style scoped>
.extend {
  width: 70%;
}
.rounded {
  border-radius: 10px;
}
.grad {
  background-image: linear-gradient(to bottom right, blue, purple);
}
</style>