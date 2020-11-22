<template>
  <div>
    <div v-for="(recipe, puppy) in recipes" v-bind:key="puppy" class="[ col-sm-12 ]">
         <recipeComponent v-bind:image="recipe.thumbnail"
                          v-bind:title="recipe.title"
                          v-bind:ingredients="recipe.ingredients"
                          v-bind:link="recipe.href"
         ></recipeComponent>
       </div>
  </div>
</template>

<script>
import recipeComponent from './components/recipeComponent.vue'
export default {
    name: 'HomePage',
    components:{
      recipeComponent
    },
    data(){
      return{
        recipes: []
      }
    },
    beforeMount: function(){
      const app= this;
    
    const conversionUrl = 'https://cors-anywhere.herokuapp.com/';
    const url = 'http://www.recipepuppy.com/api/';
      
        fetch(conversionUrl + url)
        .then(function(response) {
          return response.json();
        })
        .then(function(result) {
          app.recipes = result.results;
        })
      }
    } 
</script>


<style scoped>

body{
    color: black;
    font-family: Arial, Helvetica, sans-serif;
}


.card{
    border: solid 2px black;
    border-radius: 4px;
    padding: 0px 20px 30px;
    margin-top: 30px
}

.card img{
    width: 100%;
    padding-top: 20px;
}

</style>