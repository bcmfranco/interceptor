<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <div id="isotype">INT</div>

    <div class="wrapper">
      <h1>Interceptor</h1>
      <h2>online </h2>

      <nav>
        <RouterLink to="/">Interés simple</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

:root {
  --vue_green: #26a69a;
}

@font-face {
  font-family: 'Anton';
  src: url('assets/anton/Anton-Regular.ttf') format('truetype');
}

header{
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 25% 50% 25%;
}

#isotype {
  display: block;
  font-family: 'Anton', sans-serif;
  width: 50px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  font-size: 25px;
  color: #26a69a;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
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

@media (min-width: 1024px) {
  header{
    display: grid;
    grid-template-columns: 25% auto;
    grid-template-rows: 1fr;
    align-items: center;
  }

  #isotype{
    font-size: 50px;
  }

  header .wrapper {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 50% 25% 25%;
    align-items: center;
    height: 100px;
  }

  .wrapper h1{
    color: red;
    margin: 0px;
    padding: 0px;
  }

  .wrapper h2{
    color: red;
    margin: 0px;
    padding: 0px;
  }


  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    margin-top: 1rem;
  }
}
</style>
