<script setup>
// <select /> is the HTML element that is a dropdown
// fetchCountries same way we did for jokes
// v-for over result 
// show names of countries in dropdown
import { ref } from "vue"
const countries = ref([])
const selectedCountry = ref({})

async function fetchCountries(){
  const response = await fetch("https://restcountries.com/v3.1/all?fields=name,flags")
  const result = await response.json()
  countries.value = result
}
fetchCountries()

// function onSelected(event){
//   console.log(event.target.value)
//   selectedCountry.value = event.target.value
// }
</script>

<template>
  <div>
  <div class="" v-if="selectedCountry.name">
    <h1>Selected country: {{ selectedCountry.name }}</h1>
    <img :src="selectedCountry.flag" />
  </div>
  <div class="" v-else>
    <h1>Please select a country</h1>
  </div>

    <!-- <select @change="onSelected($event)" v-if="countries" v-model="selectedCountry"> -->
    <select v-if="countries" v-model="selectedCountry">
      <option v-for="country in countries" :value="{ name: country.name.official, flag: country.flags.png }">
        <p>{{ country.name.official }}</p>
      </option>
    </select>
  </div>
</template>