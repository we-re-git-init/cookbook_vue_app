<template>
  <div class="home">
    <h1>{{ message }}</h1>
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
      recipes: []
    };
  },
  created: function() {
    console.log('i am in created');
    axios.get("/api/recipes").then(response => {
      console.log(response.data);
      this.recipes = response.data;
    })
  },
  methods: {}
};
</script>

