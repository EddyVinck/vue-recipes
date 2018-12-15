<template>
  <div class="recipes">
    <h1>Recipes</h1>
    <ul>
      <li v-for="(recipe, i) in recipes" :key="i">
        <h2>{{ recipe.name }}</h2>
        <ul v-if="recipe.ingredients.length">
          <li
            v-for="(ingredient, ii) in recipe.ingredients"
            :key="ii"
          >{{ ingredient.name }} - {{ ingredient.quantity }}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["recipes"],
  data() {
    return {};
  },
  methods: {}
};
</script>
<style scoped>
</style>
