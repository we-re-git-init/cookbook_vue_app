<template>
  <div class="home">

    <div v-for="recipe in recipes">
      <p>id:{{recipe.id}}</p>
      <p>title:{{recipe.title}}</p>
      <p>image url: {{recipe.image_url}}</p>
      <img width="150px" v-bind:src="recipe.image_url" v-bind:alt="recipe.title">
      <router-link v-bind:to="`/recipes/${recipe.id}`">See more info</router-link>
      <div v-if="false">
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
    }

  }
};

// user enters information
// user clicks button
// get all information that user has typed in
// send that data to the api
// show the user the new item they have created

</script>

