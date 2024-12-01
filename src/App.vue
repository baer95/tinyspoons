<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
<!--      <RouterLink to="/about">About</RouterLink>-->
      <RouterLink to="/random-spoon">Random Spoon</RouterLink>
    </nav>
  </header>

  <RouterView />

  <footer>Built with &#x2665; by the soy yoghurt gang</footer>
</template>

<style>
header {
  line-height: 1.5;
  min-height: 1vh;
  padding: 2rem 0;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  padding: 1rem 0;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

main {
  flex-grow: 1;
  padding: 2rem;
}

footer {
  min-height: 1vh;
  text-align: center;
  padding: 1rem 0;
}

@media (min-width: 1024px) {
  header {
  }

  nav {
    font-size: 1rem;
  }

  main {}

  footer {}
}
</style>
