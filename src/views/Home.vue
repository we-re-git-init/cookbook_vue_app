<template>
  <div class="home">
    <div class="container">

    </div>
    <aside id="fh5co-hero" class="js-fullheight">
      <div class="flexslider js-fullheight">
        <ul class="slides">
          <li style="background-image: url(images/sweet_duckling.jpeg);">
            <div class="overlay-gradient"></div>
            <div class="container">
              <div class="col-md-10 col-md-offset-1 text-center js-fullheight slider-text">
                <div class="slider-text-inner">
                  <h2>Start Your Startup With This Template</h2>
                  <p><a href="#" class="btn btn-primary btn-lg">Get started</a></p>
                </div>
              </div>
            </div>
          </li>
          <li style="background-image: url(images/slide_2.jpg);">
            <div class="container">
              <div class="col-md-10 col-md-offset-1 text-center js-fullheight slider-text">
                <div class="slider-text-inner">
                  <h2>Take Your Business To The Next Level</h2>
                  <p><a href="#" class="btn btn-primary btn-lg">Get started</a></p>
                </div>
              </div>
            </div>
          </li>
          <li style="background-image: url(images/slide_3.jpg);">
            <div class="container">
              <div class="col-md-10 col-md-offset-1 text-center js-fullheight slider-text">
                <div class="slider-text-inner">
                  <h2>We Think Different That Others Can't</h2>
                  <p><a href="#" class="btn btn-primary btn-lg">Get started</a></p>
                </div>
              </div>
            </div>
          </li>
          </ul>
        </div>
    </aside>

    <div id="fh5co-work-section" class="fh5co-light-grey-section">
      <div class="container">
        <div class="row">
          <div class="col-md-6 col-md-offset-3 text-center fh5co-heading animate-box">
            <h2>Latest Projects</h2>
            <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-4" v-for="recipe in recipes">
            <a v-bind:href="'/recipes/' + recipe.id" class="item-grid text-center">
              <div class="image" style="background-image: url(images/image_1.jpg)"></div>
              <div class="v-align">
                <div class="v-align-middle">
                  <h3 class="title">{{ recipe.title }}</h3>
                  <h5 class="category">Web Application</h5>
                </div>
              </div>
            </a>
          </div>
          <div class="col-md-12 text-center animate-box">
            <p><a href="#" class="btn btn-primary with-arrow">View More Projects <i class="icon-arrow-right"></i></a></p>
          </div>
        </div>
      </div>
    </div>
    <div id="fh5co-testimony-section">
      <div class="container">
        <div class="row">
          <div class="col-md-6 col-md-offset-3 text-center fh5co-heading animate-box">
            <h2>Clients Feedback</h2>
            <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12 col-offset-0 to-animate">
            <div class="wrap-testimony animate-box">
              <div class="owl-carousel-fullwidth">
                <div class="item">
                  <div class="testimony-slide active text-center">
                    <figure>
                      <img src="images/person1.jpg" alt="user">
                    </figure>
                    <blockquote>
                      <p>"Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean."</p>
                    </blockquote>
                    <span>Athan Smith, via <a href="#" class="twitter">Twitter</a></span>
                  </div>
                </div>
                <div class="item">
                  <div class="testimony-slide active text-center">
                    <figure>
                      <img src="images/person2.jpg" alt="user">
                    </figure>
                    <blockquote>
                      <p>"Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean."</p>
                    </blockquote>
                    <span>Nathalie Kosley, via <a href="#" class="twitter">Twitter</a></span>
                  </div>
                </div>
                <div class="item">
                  <div class="testimony-slide active text-center">
                    <figure>
                      <img src="images/person3.jpg" alt="user">
                    </figure>
                    <blockquote>
                      <p>"Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean."</p>
                    </blockquote>
                    <span>Yanna Kuzuki, via <a href="#" class="twitter">Twitter</a></span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="fh5co-blog-section" class="fh5co-light-grey-section">
      <div class="container">
        <div class="row">
          <div class="col-md-6 col-md-offset-3 text-center fh5co-heading animate-box">
            <h2>Recent from Blog</h2>
            <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 col-sm-6 animate-box">
            <a href="#" class="item-grid">
              <div class="image" style="background-image: url(images/image_1.jpg)"></div>
              <div class="v-align">
                <div class="v-align-middle">
                  <h3 class="title">We Create Mobile App</h3>
                  <h5 class="date"><span>June 23, 2016</span> | <span>4 Comments</span></h5>
                  <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove.</p>
                </div>
              </div>
            </a>
          </div>
          <div class="col-md-6 col-sm-6 animate-box">
            <a href="#" class="item-grid">
              <div class="image" style="background-image: url(images/image_2.jpg)"></div>
              <div class="v-align">
                <div class="v-align-middle">
                  <h3 class="title">Geographical App</h3>
                  <h5 class="date"><span>June 22, 2016</span> | <span>10 Comments</span></h5>
                  <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove.</p>
                </div>
              </div>
            </a>
          </div>
          <div class="col-md-12 text-center animate-box">
            <p><a href="#" class="btn btn-primary with-arrow">View More Post <i class="icon-arrow-right"></i></a></p>
          </div>
        </div>
      </div>
    </div>
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

    <div class="fh5co-cta" style="background-image: url(images/slide_2.jpg);">
      <div class="overlay"></div>
      <div class="container">
        <div class="col-md-12 text-center animate-box">
          <h3>We Try To Update The Site Everyday</h3>
          <p><a href="#" class="btn btn-primary btn-outline with-arrow">Get started now! <i class="icon-arrow-right"></i></a></p>
        </div>
      </div>
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
      sortAttribute: 'id',
      sortOrder: 1
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
      if (attribute === this.sortAttribute) {
        this.sortOrder = this.sortOrder * -1;
      } else {
        this.sortOrder = 1;
        this.sortAttribute = attribute;
      }
    }
  }
};

</script>

