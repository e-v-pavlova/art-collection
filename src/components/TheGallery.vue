<script>
import ArtWork from "./ArtWork.vue";

export default {
    components: {
        ArtWork,
    },
    data() {
        return {
            artWorks: [],
        }
    },
    created() {
        this.fetchData();
    },
    methods: {
        async fetchData() {
            this.artWorks = await (await fetch('././api/artworks.json')).json();
        },
    }
}
</script>

<template>
    <div class="wrapper">
        <ArtWork
            v-for="artWork in artWorks"
            :title="artWork.title"
            :author="artWork.author"
            :year="artWork.year"
            :src="artWork.src"
            :layout="artWork.layout"
        ></ArtWork>
    </div>
</template>

<style scoped>
.wrapper {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: flex-end;
}
</style>
