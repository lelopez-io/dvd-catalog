<template>
    <div class="collection">
        <h1>DVD Collection</h1>
        <div v-bind:key="dvd.id" v-for="dvd in collection">
            <DVD v-bind:dvd="dvd" v-on:delete-dvd="$emit('delete-dvd', dvd.title)"/>
        </div>

    </div>
</template>

<script>
import DVD from './DVD.vue'

export default {
    name: "Collection",
    components: {
        DVD
    },
    props: ["collection"]
}
</script>

<style scoped>
.collection h1 {
    text-align: center;
}
</style>


