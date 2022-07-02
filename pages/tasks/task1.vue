<template>
  <div>
    <p>{{ count }}</p>
    <button @click="start">start</button>
    <button @click="stop">stop</button>
    <button @click="reset">reset</button>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return { count: 600, setInsfi: 0, isRunning: false }
  },
  methods: {
    start() {
      this.isRunning = true
      this.setInsfi = setInterval(() => {
        if (this.isRunning) {
          this.count--
        } else this.count = this.count
      }, 1000)
    },
    stop() {
      this.isRunning = false
      clearInterval(this.setInsfi)
    },
    reset() {
      this.count = 600
    },
  },
})
</script>
