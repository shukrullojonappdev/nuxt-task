<template>
  <div>
    <button class="btn" @click="prev" :disabled="prevBtnDisabled">Prev</button>
    <div class="panigation-list">
      <div
        v-for="page in pages"
        :key="page"
        v-bind:style="[{ display: 'inline-block' }]"
      >
        <span
          class="page"
          v-bind:style="[
            page - 1 === currentPage
              ? { border: '1px solid red', color: 'red' }
              : { border: '1px solid black', coloe: 'black' },
          ]"
          >{{ page }}</span
        >
      </div>
    </div>
    <button class="btn" @click="next" :disabled="nextBtnDisabled">Next</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  data() {
    return {
      pages: [1, 2, 3, 4, 5],
      currentPage: 0,
    };
  },
  methods: {
    next() {
      this.currentPage++;
      console.log(this.currentPage);
    },
    prev() {
      this.currentPage--;
      console.log(this.currentPage);
    },
  },
  computed: {
    prevBtnDisabled() {
      return this.currentPage === 0;
    },
    nextBtnDisabled() {
      return this.currentPage === this.pages.length - 1;
    },
  },
});
</script>

<style scoped>
.page {
  border: 1px solid black;
  padding: 3px;
  margin-right: 5px;
  display: inline-block;
}
.panigation-list {
  display: inline-block;
  margin-left: 5px;
}
</style>
