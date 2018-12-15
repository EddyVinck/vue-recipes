<template>
  <div class="home">
    <div class="container">
      <div class="recipes-wrapper">
        <Recipes v-on:delete="deleteRecipe" v-bind:recipes="recipes"/>
        <IngredientList v-on:add-recipe="addRecipe"/>
      </div>
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
    },
    deleteRecipe(index) {
      this.recipes.splice(index, 1);
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

<style>
.recipes-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.recipes {
  flex: 0 1 600px;
}
.ingredients {
  flex: 0 1 400px;
}
@media (max-width: 1100px) {
  .recipes {
    flex: 0 1 59%;
  }
  .ingredients {
    flex: 0 1 39%;
  }
}
@media (max-width: 768px) {
  .recipes-wrapper {
    flex-direction: column;
  }
  .recipes,
  .ingredients {
    flex: 0 1 100%;
    width: 100%;
  }
}
</style>

