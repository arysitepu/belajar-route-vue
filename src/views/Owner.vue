<script setup>
import { useRoute, RouterView } from 'vue-router';
import products from "../data/products.json"
const route = useRoute();
const {owner} = products.find((p) => p.id === parseInt(route.params.id));
</script>

<template>
    <div v-if="owner">
        <h1>Owner</h1>
        <p>{{ owner.name }}</p>
        <p>{{ owner.email }}</p>
    </div>
    <div v-else>Owner not found</div>
</template>