<template>
    <div class="recipe-card">
      <!-- Displaying the image using the URL from the recipe -->
     
      <h3>{{ recipe.name }}</h3>
      <img :src="recipe.image" :alt="recipe.name" class="recipe-image" />
      <p><strong>Ingredients:</strong> {{ recipe.ingredients.join(', ') }}</p>
      <p><strong>Steps:</strong> {{ recipe.steps.join(' -> ') }}</p>
      <p><strong>Cooking Time:</strong> {{ recipe.cookingTime }}</p>
      
    </div>
  </template>
  
  <script>
  export default {
    props: {
      recipe: Object  // The 'recipe' prop will hold the recipe data passed from RecipeList
    }
  };
  </script>
  
  <style scoped>
  .recipe-card {
    width: 230px;
    border: 1px solid #ddd;
    padding: 20px;
    height: 600px;
    margin: 10px;
    border-radius: 10px;
    text-align: center;
    border-color: black;
    background-color: white;
  }
  
  .recipe-image {
  width: 100%;
  height: 40%;
  border-radius: 8px;
  margin: 16px 0;
  display: block;
}
  
  .recipe-card h3 {
    margin-top: 10px;
    font-size: 1.2em;
  }
  </style>