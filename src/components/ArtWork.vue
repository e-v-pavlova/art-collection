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
    <div class="artwork">
        <img class="artwork__image" :src = "src"/>
        <div class="artwork__title">{{ title }}</div>
        <div class="artwork__author">{{ author }}</div>
        <div class="artwork__year">{{ year }}</div>
    </div>
</template>

<style scoped>
img {
    max-width: 300px;
}
.artwork {
    padding: 20px;
}
</style>
