<template>
    <div>
      <!-- <ToDoList /> -->
      <h1>{{ joke.quote }}</h1>
  
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue"
  // import ToDoList from "./components/ToDoList.vue";
  const joke = ref("")
  
  async function fetchJoke() {
    const response = await fetch("https://api.kanye.rest/")
    const result = await response.json()
    joke.value = result
  }
  
  fetchJoke()
  </script>
  