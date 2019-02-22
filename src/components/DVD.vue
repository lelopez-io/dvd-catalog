<template>
    <div class="dvd">
        <h3>{{dvd.title}}</h3>
        <p class="dvd-info">
            Category: {{dvd.category}}<br/>
            Runtime: {{dvd.runtime}}min<br/>
            Year: {{dvd.year}}<br/>
            Price: ${{dvd.price}}<br/>
        </p>
        <p class="dvd-btns">
            <!-- <button class="edit">edit</button> -->
            <button @click="$emit('delete-dvd', dvd.title)" 
                class="delete">delete</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "DVD",
    props: ["dvd"]
}
</script>

<style scoped>
.dvd {
    text-align: left;
    margin: 0 1em;
}

.dvd h3 {
    margin-bottom: .5em;
}

.dvd p {
    margin: 0;
    margin-left: 1em;
}

.dvd-btns button {
    margin-right: 1em;
}
</style>
