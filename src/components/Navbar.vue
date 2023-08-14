<script setup>
  import { RouterLink } from 'vue-router';
</script>
<template>
  <header>
    <RouterLink to="/" class="logo">
      <img src="../assets/logo.png" alt="logo" width="50">
      <h1>Pokedéx</h1>
    </RouterLink>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="about">About</RouterLink>
    </nav>
  </header>
</template>
<style scoped>
  header {
    padding: 0 5%;
    display: flex;
    justify-content: space-between;
    background-color: #222;
    height: 100px;
    border-bottom: 2px solid black;
    margin-bottom: 20px;
  }
  .logo {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    color: #fff;
  }
  nav {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
  }
  nav a {
    text-decoration: none;
    font-size: 20px;
    transition: .5s;
    color: #fff;
  }
  nav a:hover {
    color: rgb(175, 37, 37);
  }
</style>