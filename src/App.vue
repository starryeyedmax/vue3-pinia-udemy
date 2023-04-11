<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav class="navbar bg-dark navbar-dark">
    <div class="container">
      <RouterLink class="navbar-brand" to="/">
        <img src="@/assets/logo.svg" alt="Bootstrap" width="30" height="24" class="d-inline-block align-text-top" />
        PokeApi
      </RouterLink>
      <div>
        <RouterLink class="btn btn-outline-primary me-2" to="/about">About</RouterLink>
        <RouterLink class="btn btn-outline-primary me-2" to="/pokemons">Pokemons</RouterLink>
        <RouterLink class="btn btn-outline-primary" to="/favoritos">Favoritos</RouterLink>

      </div>
    </div>
  </nav>
  <div class="container text-center">
    <RouterView />
  </div>
</template>

