<script setup>
defineProps({
    title: {
        type: String,
        required: true,
    },
    author: {
        type: String,
        required: true,
    },
    year: {
        type: String,
        required: false,
    },
    src: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <h1>{{ title }}</h1>
    <div>{{ author }}</div>
    <div>{{ year }}</div>
    <img :src = "src"/>
</template>

<style scoped>
img {
    max-width: 300px;
}
</style>