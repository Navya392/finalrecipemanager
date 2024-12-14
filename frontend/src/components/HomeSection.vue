<template>
      <main class="main-content">
       <div>
          <RecipeList/>
        </div>
      </main>
  </template>
  
  <script>

  import RecipeList from './RecipeList.vue';
  export default {
    name: "HomeSection",
    components: {
        RecipeList
    }
  };
  </script>
  
  <style scoped>
  .main-content {
    flex: 1;
    background-color: #c7e8ac;
    padding: 40px;
  }
  </style>
  