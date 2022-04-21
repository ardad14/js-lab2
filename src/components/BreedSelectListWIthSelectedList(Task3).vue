<template>
    <div class="container">
        <h4 v-if="title !== undefined">{{ title }}</h4>
        <h4 v-else>Заголовок по умолчанию</h4>
        <select id="mainList" v-model="selectedBreeds" :style="styles" multiple>
            <option v-for="breed in breeds" :key="breed.message">
                {{ breed }}
            </option>
        </select>
        <h3>Выбранные породы</h3>
        <BreedSelectListWithoutData :breeds="this.selectedBreeds" :styles="styles"/>
    </div>
</template>

<script>
import BreedSelectListWithoutData from "@/components/BreedSelectListWithoutData(Task2)";

export default {
    name: "BreedSelectListWIthSelectedList",
    components: {
        BreedSelectListWithoutData
    },
    props: {
        breeds: [],
        title: String,
        styles: Object
    },
    data: () => ({
        selectedBreeds: []
    })
}
</script>

<style scoped>

</style>