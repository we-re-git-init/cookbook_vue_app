

<template>
  <div class="home">
    <h1>id: {{ recipe.id }}</h1>
    <h1>title: {{ recipe.title }}</h1>
    <h1>directions: {{ recipe.directions }}</h1>
    <h1>ingredients: {{ recipe.ingredients }}</h1>
    <h1>prep_time: {{ recipe.prep_time }}</h1>
    <button v-on:click="destroyRecipe()">Destroy the recipe</button>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios"

export default {
  data: function() {
    return {
      message: "Welcome to Show!",
      recipe: {}
    };
  },
  created: function() {
    // console.log(this.$route.params.id);
    axios.get(`/api/recipes/${this.$route.params.id}`).then(response => {
      console.log(response.data);
      this.recipe = response.data;
    })
  },
  methods: {
    destroyRecipe: function() {
      axios.delete('/api/recipes/' + this.recipe.id).then(response => {
        this.$router.push('/')
      })
    }
  }
};
</script>
