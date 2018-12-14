<template>
  <div class="home">
    <div class="container">
      <Recipes/>
      <IngredientList/>
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
  }
};
</script>
