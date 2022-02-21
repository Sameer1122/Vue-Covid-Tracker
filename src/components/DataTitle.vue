<template>
  <div class="flex flex-col items-center justify-center space-y-4 mb-4">
    <div class="font-bold text-xl">{{ text }}</div>
    <div class="font-bold text-gray-400">{{ timestamp }}</div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "DataTitle",
  props: ["text", "date"],
  computed: {
    timestamp: function () {
      return moment(this.date).format("MM Do YY, h:mm:ss a");
    },
  },
};
</script>

<style scoped></style>
