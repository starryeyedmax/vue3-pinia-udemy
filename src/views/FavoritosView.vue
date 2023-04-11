<template>
    <h1>Favoritos</h1>
    <p v-if="favoritos.length === 0">Sin favoritos</p>
    <ul class="list-group" v-else>
        <li v-for="poke in favoritos" :key="poke.id" class="list-group-item">
            <div>{{ poke.id }} - {{ poke.name }}</div>
            <router-link class="btn btn-sm btn-outline-primary me-2" :to="`/pokemons/${poke.name}`">
                Más info
            </router-link>
            <button class="btn btn-sm btn-outline-danger" @click="remove(poke.id)">
                Eliminar
            </button>
        </li>
    </ul>
</template>

<script setup>
import { useFavoritoStore } from "@/store/favoritos";
import { storeToRefs } from "pinia";

const useFavorito = useFavoritoStore();

const { favoritos } = storeToRefs(useFavorito);
const { remove } = useFavorito;
</script>