<template>
  <div class="has-background-grey-lighter" style="height: 100vh">
    <NavBar />
    <div class="box m-5" style="height: 85%">
      <div class="columns m-1">
        <div class="column is-4 has-text-left">
          <div class="title is-size-4">MANAGE VEHICLE</div>
          <div class="subtitle">Select a Vehicle Make and Year</div>
          <b-dropdown aria-role="list">
            <template #trigger="{ active }">
              <b-button
                label="Select Make"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>

            <b-dropdown-item aria-role="listitem">BMW</b-dropdown-item>
            <b-dropdown-item aria-role="listitem">Honda</b-dropdown-item>
            <b-dropdown-item aria-role="listitem">Hundai</b-dropdown-item>
          </b-dropdown>
          <b-dropdown aria-role="list">
            <template #trigger="{ active }">
              <b-button
                label="Select Year"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>

            <b-dropdown-item aria-role="listitem">2020</b-dropdown-item>
            <b-dropdown-item aria-role="listitem">2021</b-dropdown-item>
            <b-dropdown-item aria-role="listitem">2022</b-dropdown-item>
          </b-dropdown>
        </div>
        <div class="column is-2 has-text-right is-offset-7">
          <div class="buttons">
            <b-button rounded type="is-primary">Add New </b-button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
export default {
  name: "ManageVehicle",
  components: {
    NavBar,
  },
};
</script>

<style>
</style>