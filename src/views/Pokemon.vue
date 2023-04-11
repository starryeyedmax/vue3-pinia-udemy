<template>
    <main class="text-center">
        <p v-if="loading">Cargando...</p>
        <div class="alert alert-danger mt-2" v-if="error">{{ error }}</div>
        <div v-if="data">
            <img :src="data?.sprites?.front_default" alt="" />
            <h1>Poke: {{ $route.params.name }}</h1>
            <button class="btn btn-outline-primary mb-2" :disabled="findPoke(data.name)" @click="add(data)">Agregar a
                Favoritos</button>
        </div>
        <h1 v-else>Pokemon no encontrado...</h1>
        <button @click="back()">Volver al listado</button>
    </main>
</template>

<script setup>
import { useRoute, useRouter } from "vue-router";
import { useGetData } from '@/composables/getData'
import { useFavoritoStore } from "@/store/favoritos";


const route = useRoute();
const router = useRouter();
const useFavorito = useFavoritoStore();
const { data, getData, loading, error } = useGetData();
const { add, findPoke } = useFavorito;

const back = () => {
    router.push("/pokemons");
};

getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`);
</script>