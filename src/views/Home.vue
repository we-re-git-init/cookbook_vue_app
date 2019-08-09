<template>
  <div class="home">
    <p>Search: <input type="text" v-model="searchTerm" list="titles"></p>
    <p><button v-on:click="setSortAttribute('prep_time')">Sort by prep time</button></p>
    <p><button v-on:click="setSortAttribute('title')">Sort by title</button></p>
    <datalist id="titles">
      <option v-for="recipe in recipes">{{recipe.title}}</option>

    </datalist>
    <!-- <div v-for="recipe in orderBy(recipes, sortAttribute)"> -->
    <div v-for="recipe in orderBy(filterBy(recipes, searchTerm, 'title'), sortAttribute)">
      <p>id:{{recipe.id}}</p>
      <p>title:{{recipe.title}}</p>
      <p>prep_time:{{recipe.prep_time}}</p>
      <p>image url: {{recipe.image_url}}</p>
      <img width="150px" v-bind:src="recipe.image_url" v-bind:alt="recipe.title">
      <p><router-link v-bind:to="`/recipes/${recipe.id}`">See more info</router-link></p>
      <hr>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios"
import Vue2Filters from "vue2-filters";

export default {
  mixins: [Vue2Filters.mixin],
  data: function() {
    return {
      message: "change.js!",
      recipes: [],
      searchTerm: "",
      sortAttribute: 'id'
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
    setSortAttribute: function(attribute) {
      console.log(attribute);
      this.sortAttribute = attribute;
    }
  }
};

</script>

