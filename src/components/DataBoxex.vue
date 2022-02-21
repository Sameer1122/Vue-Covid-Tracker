<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box1 -->
    <div class="bg-blue-500 shadow-md p-10 text-center rounded">
      <h3 class="text-2xl font-bold text-white">Cases</h3>
      <div class="text-2xl text-white">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl text-white">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>
    <!-- Box 2 -->
    <div class="bg-blue-500 shadow-md p-10 text-center rounded">
      <h3 class="text-2xl font-bold text-white">Deaths</h3>
      <div class="text-2xl text-white">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="text-2xl text-white">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DataBoxex",
  props: ["stats"],
  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
};
</script>

<style scoped></style>
