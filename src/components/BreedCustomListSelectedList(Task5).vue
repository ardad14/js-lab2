<template>
    <div>
        <div v-for="(breed, index) in breeds" :key="index">
            <p :id="index">{{ breed }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "BreedCustomListSelectedList(Task5)",
    props: {
        breeds: Array
    }
}
</script>

<style scoped>

</style>