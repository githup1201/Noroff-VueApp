<template>
        <div class="[ card ]">
            <div class="[ row ]">
                 <div class="[ col-sm-4 ]"><img :src="image" /><br /><br /><br /></div>
                 <div class="[ col-sm-4 ]"></div>
            </div>
               <div class="[ card--information ]"><br /> 
                  
              </div>
        </div>   
</template>

<script>
export default {
    name: 'recipeComponent',
    props: ['image', 'title', 'link', 'ingredients'],
}

</script>


<style scoped>
.card{
    border: solid 1px black;
    border-radius: 4px;
    padding: 0px 20px 30px;
    margin-top: 30px;
}

.card img{
    width: 100%;
    padding-top: 20px;
}
