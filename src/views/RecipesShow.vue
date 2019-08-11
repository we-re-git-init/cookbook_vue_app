

<template>
  <div class="home">

  <div id="fh5co-pricing-section">
    <div class="container">
      <div class="row">
        <div class="col-md-6 col-md-offset-3 text-center fh5co-heading animate-box">
          <h2>Pricing</h2>
          <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
        </div>
      </div>
      <div class="row">
        <div class="pricing">
          <div class="col-md-3 animate-box">
            <div class="price-box">
              <h2 class="pricing-plan">Starter</h2>
              <div class="price"><sup class="currency">$</sup>9<small>/month</small></div>
              <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
              <a href="#" class="btn btn-select-plan btn-sm">Select Plan</a>
            </div>
          </div>

          <div class="col-md-3 animate-box">
            <div class="price-box">
              <h2 class="pricing-plan">Basic</h2>
              <div class="price"><sup class="currency">$</sup>27<small>/month</small></div>
              <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
              <a href="#" class="btn btn-select-plan btn-sm">Select Plan</a>
            </div>
          </div>

          <div class="col-md-3 animate-box">
            <div class="price-box popular">
              <h2 class="pricing-plan pricing-plan-offer">Pro <span>Best Offer</span></h2>
              <div class="price"><sup class="currency">$</sup>74<small>/month</small></div>
              <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
              <a href="#" class="btn btn-select-plan btn-sm">Select Plan</a>
            </div>
          </div>

          <div class="col-md-3 animate-box">
            <div class="price-box">
              <h2 class="pricing-plan">Unlimited</h2>
              <div class="price"><sup class="currency">$</sup>140<small>/month</small></div>
              <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
              <a href="#" class="btn btn-select-plan btn-sm">Select Plan</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
    <h1>id: {{ recipe.id }}</h1>
    <h1>title: {{ recipe.title }}</h1>
    <h1>directions: {{ recipe.directions }}</h1>
    <h1>ingredients: {{ recipe.ingredients }}</h1>
    <h1>prep_time: {{ recipe.prep_time }}</h1>
    <button v-on:click="destroyRecipe()">Destroy the recipe</button>
    <router-link v-bind:to="`/recipes/${recipe.id}/edit`">Edit recipe</router-link>
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
