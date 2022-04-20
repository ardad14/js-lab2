<template>
    <div>
        <select multiple>
            <option v-for="breed in Object.keys(this.allBreeds)" :key="breed.message">
                {{ breed }}
            </option>
        </select>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: 'BreedSelectList',
    data() {
        return {
            allBreeds: []
        }
    },
    mounted() {
        axios
            .get('https://dog.ceo/api/breeds/list/all')
            .then(response => {
                this.allBreeds = response.data.message;
            })
            .catch(error => {
                console.log(error);
            })
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

select {
    height: 300px;
}

</style>
