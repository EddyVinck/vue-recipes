<template>
  <section class="ingredients">
    <div class="top">
      <h1>Ingredients</h1>
    </div>
    <ul v-if="ingredients.length">
      <li v-for="ingredient in ingredients" :key="ingredient.name">
        <strong>{{ ingredient.name }}</strong>
        <span class="quantity">{{ ingredient.quantity }}</span>
      </li>
    </ul>
    <p class="no-ingredients" v-else>No ingredients available.</p>
    <div class="bottom">
      <div class="button-container">
        <button v-on:click="showAddIngredientForm" class="button" type="button">Add ingredient</button>
        <button
          v-on:click="saveRecipe"
          class="button button--secondary"
          type="button"
        >Save as recipe</button>
      </div>
      <form v-if="showForm" v-on:submit.prevent="handleFormSubmit">
        <input
          v-model="new_ingredient.name"
          type="text"
          name="ingredient"
          placeholder="Pasta"
          id="ingredient"
        >
        <input
          v-model="new_ingredient.quantity"
          type="text"
          name="quanity"
          placeholder="200 gr"
          id="quanity"
        >
        <button class="button" type="submit" v-on:submit.prevent="handleFormSubmit">Add</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: "IngredientList",
  props: {},
  data() {
    return {
      showForm: false,
      new_ingredient: {
        name: "",
        quantity: ""
      },
      ingredients: [
        {
          name: "pasta",
          quantity: "300 grams"
        },
        {
          name: "sauce",
          quantity: "500 ml"
        }
      ]
    };
  },
  methods: {
    showAddIngredientForm() {
      console.log("show form");
      this.showForm = true;
    },
    handleFormSubmit(event) {
      console.log(event);
      console.log("submit ingredient!");

      const { name, quantity } = this.new_ingredient;

      if (name !== "" && quantity !== "") {
        this.ingredients.push({
          name,
          quantity
        });
        this.showForm = false;
      } else {
        console.log("The ingredient has no specified name or quantity");
      }

      this.new_ingredient.name = "";
      this.new_ingredient.quantity = "";
    },
    saveRecipe() {
      console.log("save recipe!");
      this.ingredients = [];
    }
  }
};
</script>

<style scoped>
.ingredients {
  width: 400px;
  max-width: 100%;
  background: rgb(41, 185, 41);
  color: #fff;
  box-shadow: 0px 5px 15px 2px rgba(44, 62, 80, 0.3);
}
.top {
  padding: 30px 16px;
}
h1 {
  font-size: 2rem;
  margin: 0;
}
.quantity {
  padding-left: 16px;
  margin-left: 8px;
  position: relative;
}
.quantity::before {
  content: "-";
  position: absolute;
  left: 0;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  color: #2c3e50;
}
li {
  padding: 4px 16px;
  font-size: 1.2rem;
}
li:nth-of-type(odd) {
  background: #ffffff;
}
li:nth-of-type(even) {
  background: #eee;
}
.button-container {
  display: flex;
  justify-content: space-between;
}
.button-container .button {
  flex-basis: 46%;
  margin: 0 0 10px;
}
form {
  padding-top: 20px;
  display: flex;
  flex-wrap: nowrap;
  max-width: 100%;
  flex-direction: column;
}
input[type="text"] {
  border: none;
  background: #eee;
  border-radius: 5px;
  padding: 8px 10px;
  margin-bottom: 8px;
}
button[type="submit"] {
  margin: 5px 0;
}
.no-ingredients {
  padding: 16px;
  font-style: italic;
  font-style: 1.2rem;
  text-align: center;
}
</style>

