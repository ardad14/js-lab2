<template>
    <div>
      <div class="lab5">
        <div v-for="(breed, index) in breeds" :key="index">
          <p :id="index" v-on:click="selectBreed(index)">{{ breed }}</p>
        </div>
      </div>

        <h3>Выбранные породы</h3>
        <div>
          <BreedCustomListSelectedListTask5 :breeds="this.selectedBreeds" />
        </div>
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

            if (breed.style.backgroundColor === 'rgb(0, 227, 255)') {
                breed.style.backgroundColor = "white";
                breed.style.border =  'none'
                breed.style.padding = '0px'
                this.selectedBreeds = this.selectedBreeds.filter(element => element !== breed.innerText);
            } else {
                this.selectedBreeds.push(breed.innerText);
                breed.style.backgroundColor = "#00e3ff";
                breed.style.border = '1px solid  black'
                breed.style.padding = '10px'
                breed.style.borderRadius = '20px'
            }
        }
    }
}
</script>

<style scoped>
  .lab5{
    width: 900px;
    display: flex;
    flex-wrap:wrap;
    justify-content: space-between;
  }
  .lab5 p{
    margin-left:50px;
  }
 .selected{
   border: 1px solid black;
 }
</style>