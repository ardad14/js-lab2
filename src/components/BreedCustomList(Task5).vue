<template>
    <div>
        <div v-for="(breed, index) in breeds" :key="index">
            <p :id="index" v-on:click="selectBreed(index)">{{ breed }}</p>
        </div>

        <h3>Выбранные породы</h3>
        <BreedCustomListSelectedListTask5 :breeds="this.selectedBreeds" />
    </div>
</template>

<script>
import BreedCustomListSelectedListTask5 from "@/components/BreedCustomListSelectedList(Task5)";

export default {
    name: "BreedCustomList(Task5)",
    components: {
        BreedCustomListSelectedListTask5
    },
    props: {
        breeds: []
    },
    data: () => ({
        selectedBreeds: []
    }),
    methods: {
        selectBreed: function (index) {
            let breed = document.getElementById(index);

            if (breed.style.backgroundColor === "blue") {
                breed.style.backgroundColor = "white";
                this.selectedBreeds = this.selectedBreeds.filter(element => element !== breed.innerText);
            } else {
                this.selectedBreeds.push(breed.innerText);
                breed.style.backgroundColor = "blue";
            }
        }
    }
}
</script>

<style scoped>

</style>