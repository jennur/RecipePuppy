<template>
  <div class="recipes">
      <div v-for="recipe in recipes">
        <RecipeCard v-bind:title="recipe.title"
                    v-bind:ingredients="recipe.ingredients"
                    v-bind:thumbnail="recipe.thumbnail"
                    v-bind:href="recipe.href"
        />
      </div>
  </div>
</template>
<script>
  import RecipeCard from './RecipeCard'

  export default {
    name: 'Home',
    components: {
      RecipeCard
    },
    data() {
      return { recipes: [] }
    },
    beforeMount: function() {
      fetch('https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api/')
        .then((response) => { return response.json();})
        .then((data) => {
          console.log(data.results);
          this.recipes = data.results;
        });
    }
  }
</script>

<style scoped>
  .recipes {
    display: flex; 
    flex-direction: row; 
    flex-wrap: wrap; 
    flex: 1 1 0; 
    align-items: center; 
    justify-content: center; 
    margin: 50px auto;
    width: 90%; 
  }
  a {
    color: #42b983;
  }
</style>
