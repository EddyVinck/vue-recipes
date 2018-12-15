<template>
  <div class="home">
    <div class="container">
      <Recipes v-bind:recipes="recipes"/>
      <IngredientList v-on:add-recipe="addRecipe"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import IngredientList from "@/components/IngredientList.vue";
import Recipes from "@/components/Recipes.vue";

export default {
  name: "home",
  components: {
    IngredientList,
    Recipes
  },
  methods: {
    addRecipe(recipeName, ingredients) {
      console.log("pushing new recipe.");
      this.recipes.push({
        name: recipeName,
        ingredients
      });
    }
  },
  data() {
    return {
      recipes: [
        {
          name: "Really good pasta",
          ingredients: [
            {
              name: "pasta",
              quantity: "200 gr."
            },
            {
              name: "sauce",
              quantity: "100 ml"
            }
          ]
        },
        {
          name: "Really good pasta for two",
          ingredients: [
            {
              name: "pasta",
              quantity: "400 gr."
            },
            {
              name: "sauce",
              quantity: "200 ml"
            }
          ]
        }
      ]
    };
  }
};
</script>
