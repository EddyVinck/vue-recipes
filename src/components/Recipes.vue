<template>
  <section class="recipes">
    <h1>Recipes</h1>
    <ul>
      <li class="recipe" v-for="(recipe, i) in recipes" :key="i">
        <h2>{{ recipe.name }}</h2>
        <ul v-if="recipe.ingredients.length">
          <li
            v-for="(ingredient, ii) in recipe.ingredients"
            :key="ii"
          >{{ ingredient.name }} - {{ ingredient.quantity }}</li>
        </ul>
        <button class="delete-button" @click="$emit('delete', i)">X</button>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: ["recipes"]
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
h1 {
  margin: 0 0 20px;
}
h2 {
  margin: 0 0 10px;
}
.recipes {
  max-width: 100%;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0px 5px 15px 2px rgba(44, 62, 80, 0.3);
  margin-bottom: 30px;
  background: #fff;
}
.recipe {
  padding: 20px;
  transition: 0.1s;
  position: relative;
}
.recipe:nth-of-type(odd) {
  background: #eeeeee;
}
.recipe:hover {
  background-color: rgb(222, 240, 255);
  cursor: pointer;
}
.recipe li {
  padding: 5px 0;
}
.delete-button {
  position: absolute;
  top: 10px;
  right: 15px;
  background: rgb(54, 54, 54);
  color: #fff;
  height: 24px;
  width: 24px;
  border-radius: 24px;
  border: none;
  font-weight: bold;
  transition: 0.2s;
  cursor: pointer;
}
.delete-button:hover {
  background: #000;
}
</style>
