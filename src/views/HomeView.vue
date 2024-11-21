<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <main>
    <h1 class="title">Need a pick-me-up? Click <RouterLink to="/random-spoon">here</RouterLink>!</h1>
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
}
h1.title {
}
</style>
