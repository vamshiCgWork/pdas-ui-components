<template>
  <div class="has-background-grey-lighter" style="height: 100vh">
    <NavBar />
    <div class="box m-5" style="height: 85vh">
      <div class="columns m-1">
        <div class="column is-7 has-text-left">
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
          <b-dropdown aria-role="list" v-model="selectModel">
            <template #trigger="{ active }">
              <b-button
                :label="selectModel.text"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>
            <b-dropdown-item
              v-for="(model, index) in models"
              :key="index"
              :value="model"
              aria-role="listitem"
            >
              {{ model.text }}
            </b-dropdown-item>
          </b-dropdown>
          <b-dropdown aria-role="list" v-model="selectVariant">
            <template #trigger="{ active }">
              <b-button
                :label="selectVariant.text"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>
            <b-dropdown-item
              v-for="(variant, index) in variants"
              :key="index"
              :value="variant"
              aria-role="listitem"
            >
              {{ variant.text }}
            </b-dropdown-item>
          </b-dropdown>
          <b-dropdown aria-role="list" v-model="selectPaint">
            <template #trigger="{ active }">
              <b-button
                :label="selectPaint.text"
                :icon-right="active ? 'menu-up' : 'menu-down'"
              />
            </template>
            <b-dropdown-item
              v-for="(paint, index) in paints"
              :key="index"
              :value="paint"
              aria-role="listitem"
            >
              {{ paint.text }}
            </b-dropdown-item>
          </b-dropdown>
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
          <b-button rounded type="is-primary" style="float: right"
            >Submit</b-button
          >
        </section>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
export default {
  name: "ManageParts",
  components: {
    NavBar,
  },
  data() {
    return {
      data: [
        {
          part: "Main Part",
          id: "52159-0U912",
          first_name: "$ 500.22",
          last_name: "$ 800.22",
          date: "$ 10.22",
          gender: "$ 32.22",
        },
        {
          part: "Cover Fender FL",
          id: "52159-0U912",
          first_name: "$ 200.22",
          last_name: "$ 100.22",
          date: "$ 8.22",
          gender: "$ 12.22",
        },
        {
          part: "Cushion Fender FL",
          id: "54159-0U912",
          first_name: "$ 154.22",
          last_name: "$ 100.22",
          date: "$ 15.22",
          gender: "$ 58.22",
        },
        {
          part: "Lining Fender FL",
          id: "54159-0U912",
          first_name: "$ 154.22",
          last_name: "$ 100.22",
          date: "$ 15.22",
          gender: "$ 58.22",
        },
      ],
      columns: [
        {
          field: "part",
          label: "",
        },
        {
          field: "id",
          label: "OEM",
        },
        {
          field: "first_name",
          label: "Part Price",
        },
        {
          field: "last_name",
          label: "R & R Units",
        },
        {
          field: "date",
          label: "Paint Labour",
        },
        {
          field: "gender",
          label: "Paint Material",
        },
      ],
      isOpen: 1,
      collapses: [
        { title: "Fender Front Left" },
        { title: "Fender Front Right" },
        { title: "Door Front Right" },
        { title: "Door Front Left" },
        { title: "Bumper" },
        { title: "Windshield" },
        { title: "Rear Bumper" },
        { title: "Hood" },
        { title: "Door Handle Rear Right" },
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
      selectModel: { text: "Select Model" },
      models: [
        { text: "Accord" },
        { text: "Acura" },
        { text: "Amaze" },
        { text: "Brio" },
      ],
      selectVariant: { text: "select Variant" },
      variants: [
        { text: "L" },
        { text: "EL" },
        { text: "SE" },
        { text: "R-Line" },
        { text: "SEL" },
      ],
      selectPaint: { text: "Select Paint" },
      paints: [{ text: "solid" }, { text: "metalic" }, { text: "Pearl" }],
    };
  },
};
</script>

<style>
</style>