<template>
  <div
    v-on:click="$emit('clickCat', catName)"
    v-bind:class="[
      'cat-container',
      selectedCatName && selectedCatName !== catName && 'unselected',
    ]"
  >
    <img :src="catImg" />
    <p>{{ catName }}</p>
  </div>
</template>

<script>
export default {
  name: "CatContainer",
  props: {
    selectedCatName: String,
    catImg: String,
    catName: String,
  },
  data() {
    return {
      publicPath: process.env.BASE_URL,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img {
  border-radius: 40px;
  padding: 20px;
  height: 200px;
  width: 200px;
  margin: auto;
  transition: transform 500ms;
}
p {
  font-family: "Oswald";
  font-weight: 700;
  font-size: 30px;
  margin: 12px;
  transition: transform 500ms;
}
.cat-container {
  margin: auto;
  width: fit-content;
  cursor: pointer;
}
.cat-container:hover img,
.cat-container:hover p {
  transform: scale(1.1);
}
.unselected {
  opacity: 0.5;
}
</style>
