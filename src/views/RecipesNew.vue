<template>
  <div class="recipes-new">
    <h1>{{ message }}</h1>
    <form v-on:submit.prevent="makeRecipe()">
      <p>Title: <input type="text" v-model="newRecipeTitle"></p>
      <p>Directions: <input type="text" v-model="newRecipeDirections"></p>
      <p>Ingredients: <input type="text" v-model="newRecipeIngredients"></p>
      <p>ImageUrl: <input type="text" v-model="newRecipeImageUrl"></p>
      <p>PrepTime: <input type="text" v-model="newRecipePrepTime"></p>
      <input type="submit" value="Create a new recipe">
    </form>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios"

export default {
  data: function() {
    return {
      message: "Welcome to the recipes new page!",
      newRecipeTitle: "",
      newRecipeDirections: "",
      newRecipeIngredients: "",
      newRecipeImageUrl: "",
      newRecipePrepTime: ""
    };
  },
  created: function() {},
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
        this.$router.push('/');
      })
    }
  }
};
</script>
