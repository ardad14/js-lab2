<template>
    <h1>Задание 1</h1>
    <BreedSelectList/>

    <h1>Задание 2</h1>
    <BreedSelectListWithoutData :breeds="Object.keys(allBreeds)" title="Заголовок" :styles=this.styleObject />

    <h1>Задание 3</h1>
    <BreedSelectListWIthSelectedList :breeds="Object.keys(allBreeds)" title="Второй заголовок" :styles=this.styleObject />

    <h1>Задание 5</h1>
    <BreedCustomListTask5 :breeds="Object.keys(allBreeds)" />
</template>

<script>
import BreedSelectList from "@/components/BreedSelectList(Task1)";
import BreedSelectListWithoutData from "@/components/BreedSelectListWithoutData(Task2)";
import BreedSelectListWIthSelectedList from "@/components/BreedSelectListWIthSelectedList(Task3)";
import BreedCustomListTask5 from "@/components/BreedCustomList(Task5)";
import axios from "axios";

export default {
    name: 'App',
    components: {
        BreedSelectList,
        BreedSelectListWithoutData,
        BreedSelectListWIthSelectedList,
        BreedCustomListTask5
    },
    data() {
        return {
            allBreeds: [],
            styleObject: {
                color: 'red',
                fontSize: '20px'
            }
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

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
