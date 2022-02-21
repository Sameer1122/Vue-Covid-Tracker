<template>
  <select
    v-model="selected"
    @change="onChange()"
    class="mt-10 block w-full border p-3 rounded"
  >
    <option value="0">Select a Country</option>
    <option v-for="country in countries" :key="country.ID" :value="country.ID">
      {{ country.Country }}
    </option>
  </select>
</template>

<script>
export default {
  name: "SelectCountries",
  props: ["countries"],
  data() {
    return {
      selected: 0,
    };
  },
  methods: {
    onChange() {
      const country = this.countries.find((item) => item.ID === this.selected);
      this.$emit("get-country", country);
    },
  },
};
</script>

<style scoped></style>
