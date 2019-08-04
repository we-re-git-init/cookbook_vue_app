<template>
  <div class="home">
    {{recipes}}
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
      <img width="150px" v-bind:src="recipe.image_url" v-bind:alt="recipe.title">
      <p><button v-on:click="setRecipe(recipe)">Show more info</button></p>
      <div v-if="currentRecipe === recipe">
        <p>directions: {{ recipe.directions }}</p>
        <p>ingredients {{ recipe.ingredients }}</p>
        <p>prep time {{ recipe.prep_time }}</p>

        <p>Title: <input type="text" v-model="recipe.title"></p>
        <p>Directions: <input type="text" v-model="recipe.directions"></p>
        <p>Ingredients: <input type="text" v-model="recipe.ingredients"></p>
        <p>ImageUrl: <input type="text" v-model="recipe.image_url"></p>
        <p>PrepTime: <input type="text" v-model="recipe.prep_time"></p>
        <button v-on:click="updateRecipe(recipe)">Update the recipe</button>
        <hr>
        <hr>
        <hr>
        <button v-on:click="destroyRecipe(recipe)">Destroy the recipe</button>
        <hr>
        <hr>
      </div>
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
      newRecipePrepTime: "",
      currentRecipe: {}
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
      }).catch(error => {
        console.log(error.response.data);
      })
    },
    setRecipe: function(theRecipe) {
      console.log('setting the recipe');
      // change the value of currentRecipe
      console.log(theRecipe);
      this.currentRecipe = theRecipe;
    },
    updateRecipe: function(theRecipe) {
      console.log('in updating recipe...');
      // get the data the user entered
      console.log(theRecipe);
      // send that data to the api
      axios.patch('/api/recipes/', theRecipe).then(response => {
        console.log(response.data);
        // replace the old data on the html page with the new data from the db
        theRecipe.title = response.data.title;
        theRecipe.directions = response.data.directions;
        theRecipe.prep_time = response.data.prep_time;
        theRecipe.ingredients = response.data.ingredients;
        theRecipe.image_url = response.data.image_url;
      })
    },
    destroyRecipe: function(theRecipe) {
      console.log('destroying recipe');
      // figure out which recipe I want to delete
      console.log(theRecipe)
      // tell the api i want to delete that recipe
      axios.delete('/api/recipes/' + theRecipe.id).then(response => {
        console.log(response.data);
        // tell the html page to delete the recipe
        // remove theRecipe from the recipes array
        var index = this.recipes.indexOf(theRecipe);
        this.recipes.splice(index, 1);
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

