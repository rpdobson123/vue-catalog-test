<template>
  <div class="app-container">
    <div class="cat-selection">
      <CatContainer
        v-on:clickCat="selectedCatName = $event"
        :selectedCatName="selectedCatName"
        v-for="cat in cats"
        v-bind:key="cat.catName"
        v-bind:catColor="cat.catColor"
        v-bind:catImg="cat.catImg"
        v-bind:catName="cat.catName"
      />
    </div>
    <template v-if="!selectedCatName">
      <p>
        Welcome to Richard's Cat-alog. Select a cat to learn more.
      </p>
    </template>
    <CatFacts :catName="selectedCatName" v-if="selectedCatName" />
  </div>
</template>

<script>
import CatContainer from "./CatContainer.vue";
import CatFacts from "./CatFacts.vue";

export default {
  name: "CatSelection",
  data: function() {
    return {
      selectedCatName: null,
      cats: [
        { catImg: "sicily.png", catName: "Sicily" },
        { catImg: "bella.png", catName: "Bella" },
      ],
    };
  },
  components: {
    CatContainer,
    CatFacts,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cat-selection {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  grid-gap: 50px;

  margin: auto;
  max-width: 1000px;
}
p {
  margin: 40px 0 24px;
  font-family: "Oswald", sans-serif;
  font-size: 24px;
}
</style>
