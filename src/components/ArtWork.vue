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
    layout: {
        type: String,
        required: false,
        default: "horizontal",
    },
});
</script>

<template>
    <div class="artwork">
        <img
            class="artwork__image"
            :class= "`artwork__image_${layout}`"
            :src = "src"
        />
        <div class="artwork__title">{{ title }}</div>
        <div class="artwork__author">{{ author }}</div>
        <div class="artwork__year">{{ year }}</div>
    </div>
</template>

<style scoped>
img {
    width: 100%;
}
.artwork {
    padding: 20px;
}

.artwork__image_horizontal {
    max-height: 300px;
}

.artwork__image_vertical {
    max-width: 300px;
}
</style>
