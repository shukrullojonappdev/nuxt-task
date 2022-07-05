<template>
  <div>{{ maxNumber }}</div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  el: "#app",
  data() {
    return {
      maxNumber: 0,
      listElements: [12, "hello", false, 345, "text", true, 254],
    };
  },
  methods: {
    getNumbers() {
      this.listElements = this.listElements.filter((e) => {
        return typeof e === "number";
      });
      console.log(this.listElements);
      this.maxNumber = Math.max(...this.listElements);
    },
  },
  mounted() {
    this.getNumbers();
  },
});
</script>
