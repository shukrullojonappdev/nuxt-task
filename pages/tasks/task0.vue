<template>
  <div>
    <p>Lowercases in text: {{ uppercase }}</p>
    <p>Count of lowercases: {{ count }}</p>
    <input
      type="text"
      v-model="message"
      placeholder="enter text"
      @change="getUppercases"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Task0Page',
  data() {
    return { message: '', uppercase: '', count: 0 }
  },
  methods: {
    getUppercases() {
      this.uppercase = this.message.replace(/[^A-Z]/g, '')
      this.count = this.uppercase.length
    },
  },
})
</script>
