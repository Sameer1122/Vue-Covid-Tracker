<template>
  <div class="flex items-center justify-center">
    <div>{{ text }}</div>
    <div>{{ timestamp }}</div>
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
