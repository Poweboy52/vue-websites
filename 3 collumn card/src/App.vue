<template>
<div class="page">
  <div class="container">
    <div class="card" :class="car.class" v-for="car in cars">
      <img class="card-image" :src="car.image" />
      
      <h1 class="card-heading">{{ car.title }}</h1>
      
      <p class="card-text">{{ car.text }}</p>
      
      <a class="card-link" :href="car.link">Learn More</a>
    </div>
  </div>
</div>
</template>

<script setup>
/* 
Bright orange: hsl(31, 77%, 52%)
Dark cyan: hsl(184, 100%, 22%)
Very dark cyan: hsl(179, 100%, 13%) 
*/

    const cars = [
      {
        image: "../src/assets/icon-sedans.svg", 
        title: "sedans",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Potenti nullam ac tortor vitae purus faucibus ornare.", 
        link: "https://www.google.com",
        class: "sedans"
      },
      {
        image: "../src/assets/icon-suvs.svg", 
        title: "suvs",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Potenti nullam ac tortor vitae purus faucibus ornare.", 
        link: "https://www.google.com",
        class: "suvs"
      },
      {
        image: "../src/assets/icon-luxury.svg", 
        title: "luxury",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Potenti nullam ac tortor vitae purus faucibus ornare.", 
        link: "https://www.google.com",
        class: "luxury"
      }
    ]

    
</script>

<style>
  .sedans {
    background-color: hsl(31, 77%, 52%);
    color: hsl(31, 77%, 52%);
  } 
  
  .suvs {
    background-color: hsl(184, 100%, 22%);
    color: hsl(184, 100%, 22%);
  }

  .luxury {
    background-color: hsl(179, 100%, 13%);
    color: hsl(179, 100%, 13%); 
  }

  .sedans .card-link:visited, 
  .sedans .card-link { 
    color: hsl(31, 77%, 52%); 
    border: 1px solid white;
  }

  .suvs .card-link:visited, 
  .suvs .card-link { 
    color: hsl(184, 100%, 22%); 
    border: 1px solid white;
  }

  .luxury .card-link:visited, 
  .luxury .card-link {
    color: hsl(179, 100%, 13%); 
    border: 1px solid white;
  }

  .sedans .card-link:hover {
    background-color: hsl(31, 77%, 52%);
    color: white;
    transition: background 500ms ease-in-out;
    border: 1px solid white;
  }

  .suvs .card-link:hover {
    background-color: hsl(184, 100%, 22%);
    color: white;
    transition: background 500ms ease-in-out;
    border: 1px solid white;
  }

  .luxury .card-link:hover {
    background-color: hsl(179, 100%, 13%);
    color: white;
    transition: background 500ms ease-in-out;
    border: 1px solid white;
  }

  .page {
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .container {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    border-radius: 8px;
    overflow: hidden;
  }
  
  .card {
    width: 200px;
    height: 100%;
    padding: 38px;
    display: flex;
    flex-direction: column;
    color: white
  }

  .card-heading {
    text-transform: uppercase;
    font-weight: 500;
    font-size: 32px;
    font-family: "Big Shoulders Display", sans-serif;
  }

  .card-image {
    max-width: 30%;
    height: auto;
  }

  .card-link {
    background-color: white;
    padding: 10px 20px;
    margin-top: 50px;
    width: fit-content;
    border-radius: 25px;
    text-decoration: none;
    font-size: 12px;
  }

  .card-link:hover {

  }

  .card-text {
    font-size: 10px;
    opacity: 0.6;
    line-height: 18px;
  }

  @media screen and (max-width: 640px){
    .container {
      flex-direction: column;
    }
    .card-link {
      margin-top: 10px
    }
  }
</style>