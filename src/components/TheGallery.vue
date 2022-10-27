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
    <ArtWork
      v-for="artWork in artWorks"
      :title="artWork.title"
      :author="artWork.author"
      :year="artWork.year"
      :src="artWork.src"
    ></ArtWork>
</template>
