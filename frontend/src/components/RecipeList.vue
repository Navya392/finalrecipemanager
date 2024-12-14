<template>
    <div class="recipe-list">
      <h1> Recipe Manager</h1>
      <div class="recipe-cards">
        <!-- Loop through recipes and pass each recipe data to RecipeCard component -->
        <RecipeCard v-for="recipe in recipes" :key="recipe.id" :recipe="recipe" />
      </div>
    </div>
  </template>
  
  <script>
  import RecipeCard from './RecipeCard.vue';
  
  export default {
    data() {
      return {
        recipes: []// Current search input  // Initialize an empty array to store recipes
      };
    },
    mounted() {
      this.fetchRecipes();  // Fetch recipes when the component is mounted
    },
    methods: {
  async fetchRecipes() {
    try {
      // Use the fetch API to get the recipes from your API
      const response = await fetch('http://localhost:9520/api');
      if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
      }
      this.recipes = await response.json(); // Parse the JSON response and store it in the recipes array
    } catch (error) {
      console.error("Error fetching recipes:", error); // Log any errors that occur
    }
  }
},
    components: {
      RecipeCard
    }
  };
  </script>
  
  <style scoped>
  .recipe-list {
    display: flex;
    flex-direction: column;
    border-radius: 20px;
    align-items: center;
    background-color: rgb(42, 79, 48);
  }

  .recipe-list h1 {
    color: white;
  }
  
  .recipe-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  </style>