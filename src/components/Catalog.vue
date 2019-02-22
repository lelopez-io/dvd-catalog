<template>
    <div id="catalog">
        <Collection v-bind:collection="DVDS" v-on:delete-dvd="deleteDVD"/>

        <AddDVD v-on:add-DVD="addDVD"/>
    </div>
    
</template>

<script>
import Collection from './Collection'
import AddDVD from './AddDVD.vue'
export default {
    name: 'Catalog',
    components: {
        Collection,
        AddDVD
    },
    data() {
        return {
            DVDS: [
                {
                    title: "Altina: Battle Angel",
                    category: "Fantasy/Science Fiction",
                    runtime: 122,
                    year: 2019,
                    price: 25.99
                }, 
                {
                    title: "Glass",
                    category: "Drama/Fantasy",
                    runtime: 129,
                    year: 2019,
                    price: 25.99
                }, 
                {
                    title: "Black Panther",
                    category: "Fantasy/Science Fiction",
                    runtime: 135,
                    year: 2018,
                    price: 19.99
                }, 
                {
                    title: "A Quite Place",
                    category: "Drama/Thriller",
                    runtime: 91,
                    year: 2018,
                    price: 19.99
                }, 
            ]
        }
    },
    methods: {
        deleteDVD(title) {
            this.DVDS = this.DVDS.filter(dvd => dvd.title !== title)
        },
        addDVD(newDVD) {
            this.DVDS = [...this.DVDS, newDVD]
        }
    }
}
</script>

<style scoped>

</style>


