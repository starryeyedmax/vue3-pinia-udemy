<template>
    <h1>ERROR 404</h1>
    <button @click="back()">Volver al listado</button>
</template>

<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const back = () => {
    router.push("/pokemons");
};
</script>