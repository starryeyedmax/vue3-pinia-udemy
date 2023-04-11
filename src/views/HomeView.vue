<template>
  <h1>Home Counter: {{ count }}</h1>
  <h2>Double: {{ double }}</h2>
  <button @click="increment">Increment</button>
</template>

<script setup>
import { useCounterStore } from "@/store/counter";
import { storeToRefs } from "pinia";

const useCounter = useCounterStore();
const { increment } = useCounter;
const { double, count } = storeToRefs(useCounter)
</script>