<template>
    <div class="[ row ]">
    <div class="[ col-sm-12 ]">
         <recipeComponent
                    
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
          app.recipes = result;
        })
    }
    }
      
    
  

</script>