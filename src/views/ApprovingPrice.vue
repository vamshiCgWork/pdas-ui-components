<template>
  <div>
    <NavBar />
    <div class="box m-5" style="height: 85vh">
      <div class="columns m-1">
        <div class="column has-text-left">
          <div class="title is-size-4">$ APPROVE PRICE</div>
          <div class="has-text-left m-1" style="height: 60vh">
            <section style="height: 50vh; overflow-y: scroll">
              <b-table :data="data" :columns="columns"></b-table>
            </section>
          </div>
          <b-button rounded style="float: right" class="is-primary"
            >Submit</b-button
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
export default {
  name: "ApprovingPrice",
  components: {
    NavBar,
  },
  data() {
    return {
      columns: [
        { field: "time", label: "Time" },
        { field: "year", label: "Year" },
        { field: "make", label: "Make" },
        { field: "model", label: "Model" },
        { field: "variant", label: "Variant" },
        { field: "edits", label: "Edits" },
      ],
      data: [
        {
          time: "12/16 3:20",
          year: "2021",
          make: "Honda",
          model: "CR-V",
          variant: "Touring",
          edits: "3",
        },
        {
          time: "12/15 1:21",
          year: "2021",
          make: "Honda",
          model: "CR-V",
          variant: "EX-L",
          edits: "2",
        },
        {
          time: "12/10 12:45",
          year: "2018",
          make: "BMW",
          model: "X5",
          variant: "Ultra",
          edits: "6",
        },
        {
          time: "12/09 10:20",
          year: "2015",
          make: "Chevrolet",
          model: "Malibu",
          variant: "LX",
          edits: "3",
        },
        {
          time: "12/09 10:20",
          year: "2015",
          make: "Audi",
          model: "Q6",
          variant: "Sport 2.6",
          edits: "3",
        },
        {
          time: "12/08 10:20",
          year: "2019",
          make: "HYNDAI",
          model: "Santa Fe",
          variant: "Rover Plus",
          edits: "3",
        },
      ],
    };
  },
};
</script>

<style>
</style>