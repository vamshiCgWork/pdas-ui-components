<template>
  <div class="has-background-grey-lighter" style="height: 100vh">
    <NavBar />
    <div class="box m-5" style="height: 85vh">
      <div class="columns m-1">
        <div class="column is-4 has-text-left">
          <div class="title is-size-4">MANAGE VEHICLE</div>
          <div class="subtitle">Select a Vehicle Make and Year</div>

          <b-dropdown v-model="selectMake" aria-role="list">
            <template #trigger="{ active }">
              <b-button
                :label="selectMake.text"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>

            <b-dropdown-item
              v-for="(make, index) in maker"
              :key="index"
              :value="make"
              aria-role="listitem"
            >
              {{ make.text }}
            </b-dropdown-item>
          </b-dropdown>

          <b-dropdown aria-role="list" v-model="selectYear">
            <template #trigger="{ active }">
              <b-button
                :label="selectYear.text"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>
            <b-dropdown-item
              v-for="(year, index) in years"
              :key="index"
              :value="year"
              aria-role="listitem"
            >
              {{ year.text }}
            </b-dropdown-item>
          </b-dropdown>
        </div>
        <div class="column is-2 has-text-right is-offset-7">
          <div class="buttons">
            <b-button rounded type="is-primary">Add New </b-button>
          </div>
        </div>
      </div>

      <div class="box has-text-left m-1" style="height: 60vh">
        <div class="title is-size-5">Vehicle Model Listing</div>
        <section style="height: 50vh; overflow-y: scroll">
          <b-collapse
            class="card"
            animation="slide"
            v-for="(collapse, index) of collapses"
            :key="index"
            :open="isOpen == index"
            @open="isOpen = index"
          >
            <template #trigger="props">
              <div class="card-header" role="button">
                <p class="card-header-title">{{ collapse.title }}</p>
                <a class="card-header-icon">
                  <b-icon :icon="props.open ? 'menu-down' : 'menu-up'">
                  </b-icon>
                </a>
              </div>
            </template>
            <div class="card-content">
              <div class="content">
                <b-table :data="data" :columns="columns"></b-table>
              </div>
            </div>
          </b-collapse>
        </section>
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
  data() {
    return {
      data: [
        {
          id: "L",
          first_name: "Hatchback",
          last_name: "Manual Transmission",
          date: "Diesel",
          gender: "Front Wheel Drive",
        },
        {
          id: 2,
          first_name: "Hatchback",
          last_name: "Automatic Transmission",
          date: "Petrol / Flex Fuel",
          gender: "Rear Wheel Drive",
        },
        {
          id: 3,
          first_name: "Hatchback",
          last_name: "Automated Manual Transmission",
          date: "Electric",
          gender: "All Wheel Drive",
        },
        {
          id: 4,
          first_name: "Hatchback",
          last_name: "Automated Manual Transmission",
          date: "Electric",
          gender: "All Wheel Drive",
        },
        {
          id: 5,
          first_name: "Hatchback",
          last_name: "Automatic Transmission",
          date: "Electric",
          gender: "All Wheel Drive",
        },
      ],
      columns: [
        {
          field: "id",
          label: "Variant",
        },
        {
          field: "first_name",
          label: "Body Type",
        },
        {
          field: "last_name",
          label: "Transmission Type",
        },
        {
          field: "date",
          label: "Fuel Type",
        },
        {
          field: "gender",
          label: "Druve Type",
        },
      ],
      isOpen: 1,
      collapses: [
        {
          title: "Accord",
          text: "Text 1",
        },
        {
          title: "Acure",
          text: "Text 2",
        },
        {
          title: "Amaze",
          text: "Text 3",
        },
        { title: "Brio" },
        { title: "BR-V" },
        { title: "City" },
        { title: "City 5th Gen" },
        { title: "City Zx" },
        { title: "Civic" },
        { title: "Civic Hybrid" },
        { title: "Concerto" },
      ],
      maxHeight: 200,
      selectMake: { text: "Select Make" },
      maker: [
        { text: "Aston Martin" },
        { text: "Bently" },
        { text: "BMW" },
        { text: "Chevrolet" },
        { text: "Ferrari" },
        { text: "Honda" },
        { text: "Hundai" },
      ],
      selectYear: { text: "Select Year" },
      years: [
        { text: "2022" },
        { text: "2021" },
        { text: "2020" },
        { text: "2019" },
        { text: "2018" },
        { text: "2017" },
        { text: "2016" },
      ],
    };
  },
};
</script>

<style>
</style>