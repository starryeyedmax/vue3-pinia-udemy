<template>
    <h1>Pokemons</h1>
    <p v-if="loading">Cargando...</p>
    <div class="alert alert-danger mt-2" v-if="error">{{ error }}</div>
    <div v-if="data">
        <ul class="list-group">
            <li class="list-group-item" v-for="poke in data.results">
                <router-link :to="`/pokemons/${poke.name}`">{{
                    poke.name
                }}</router-link>
            </li>
        </ul>
        <div class="mt-2">
            <button class="btn btn-warning me-2" :disabled="!data.previous"
                @click="getData(data.previous)">Previous</button>
            <button class="btn btn-success" :disabled="!data.next" @click="getData(data.next)">Next</button>
        </div>
    </div>
</template >

<script setup >
import { RouterLink } from "vue-router";
import { useGetData } from '@/composables/getData'

const { data, getData, loading, error } = useGetData();


getData("https://pokeapi.co/api/v2/pokemon");
</script>
