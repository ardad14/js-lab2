<template>
        <select multiple class="lab1">
            <option v-for="breed in Object.keys(this.allBreeds)" :key="breed.message">
                {{ breed }}
            </option>
        </select>
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
.lab1{
  font-size: 20px;
  padding: 10px;
  background-color: #fff;
  width: 300px;
  height: 300px;
}
</style>
