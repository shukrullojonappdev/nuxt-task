<template>
  <nav>
    <NuxtLink to="tasks/task0">task 0</NuxtLink>
    <NuxtLink to="tasks/task1">task 1</NuxtLink>
    <NuxtLink to="tasks/task2">task 2</NuxtLink>
    <NuxtLink to="tasks/task3">task 3</NuxtLink>
    <NuxtLink to="tasks/task4">task 4</NuxtLink>
  </nav>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
})
</script>
