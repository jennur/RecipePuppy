<template>
  <div class="recipe-card">
    <h3>{{ title }}</h3>
    <img :src="thumbnail" alt="Recipe image"/>
    <p><b>Ingredients: </b>{{ ingredients }}</p>
    <a :href="href">Take me to the recipe >></a>
  </div>
</template>

<script>
  export default {
    name: 'RecipeCard', 
    props: {
        title: String,
        ingredients: String,
        thumbnail: String,
        href: String
    }
  }
</script>

<style scoped>
  .recipe-card {
    width: 200px;
    min-height: 350px;
    margin: 20px; 
    background-color: #ccddff;
    padding: 25px; 
  }

  a {
    color: #42b983;
  }
</style>