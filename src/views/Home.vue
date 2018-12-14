<template>
  <div class="home">
    <div class="container">
      <IngredientList/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import IngredientList from "@/components/IngredientList.vue";

export default {
  name: "home",
  components: {
    IngredientList
  }
};
</script>
