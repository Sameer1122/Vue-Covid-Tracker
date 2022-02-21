<script>
import DataTitle from "../components/DataTitle.vue";
import DataBoxexVue from "../components/DataBoxex.vue";
import SelectCountriesVue from "../components/SelectCountries.vue";
export default {
  name: "HomeView",
  data() {
    return {
      loading: true,
      title: "Global",
      date: "",
      stats: {},
      countries: [],
    };
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = res.json();
      return data;
    },
    getCountry(country) {
      this.stats = country;
      this.title = country.Country;
    },
  },
  async created() {
    const data = await this.fetchCovidData();
    console.log(data);
    (this.loading = false),
      (this.date = data.Date),
      (this.stats = data.Global),
      (this.countries = data.Countries),
      (this.loading = false);
  },
  components: { DataTitle, DataBoxexVue, SelectCountriesVue },
};
</script>

<template>
  <main class="w-11/12 mx-auto">
    <div v-if="!loading">
      <DataTitle :date="date" :text="title" />
      <DataBoxexVue :stats="stats" />
      <SelectCountriesVue @get-country="getCountry" :countries="countries" />
    </div>
    <div v-else>Fetchingggggg</div>
  </main>
</template>
