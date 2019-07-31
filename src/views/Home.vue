<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p>Title: <input type="text" v-model="newRecipeTitle"></p>
    <p>Directions: <input type="text" v-model="newRecipeDirections"></p>
    <p>Ingredients: <input type="text" v-model="newRecipeIngredients"></p>
    <p>ImageUrl: <input type="text" v-model="newRecipeImageUrl"></p>
    <p>PrepTime: <input type="text" v-model="newRecipePrepTime"></p>
    <button v-on:click="makeRecipe()">Make a new recipe</button>
    <div v-for="recipe in recipes">
      <p>title:{{recipe.title}}</p>
      <p>image url: {{recipe.image_url}}</p>
      <img v-bind:src="recipe.image_url" v-bind:alt="recipe.title">
      <hr>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios"

export default {
  data: function() {
    return {
      message: "change.js!",
      recipes: [],
      newRecipeTitle: "",
      newRecipeDirections: "",
      newRecipeIngredients: "",
      newRecipeImageUrl: "",
      newRecipePrepTime: ""
    };
  },
  created: function() {
    console.log('i am in created');
    axios.get("/api/recipes").then(response => {
      console.log(response.data);
      this.recipes = response.data;
    })
  },
  methods: {
    makeRecipe: function() {
      console.log('in make recipe');
      // get some data
      var newRecipe = {
        title: this.newRecipeTitle,
        ingredients: this.newRecipeIngredients,
        directions: this.newRecipeDirections,
        prep_time: this.newRecipePrepTime,
        image_url: this.newRecipeImageUrl
      }
      // send that data to the api
      axios.post('/api/recipes', newRecipe).then(response => {
        console.log('in the callback for create')
        console.log(response.data);
        this.recipes.push(response.data);
      })
    }
  }
};

// user enters information
// user clicks button
// get all information that user has typed in
// send that data to the api
// show the user the new item they have created

</script>

