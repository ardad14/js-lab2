<template>
    <div>
        <h4 v-if="title !== undefined">{{ title }}</h4>
        <h4 v-else>Заголовок по умолчанию</h4>
        <select multiple :style="styles">
            <option v-for="breed in breeds" :key="breed.message">
                {{ breed }}
            </option>
        </select>
    </div>
</template>

<script>
export default {
    name: "BreedSelectListWithoutData",
    props: {
        breeds: [],
        title: String,
        styles: Object
    }
}
</script>

<style scoped>

</style>