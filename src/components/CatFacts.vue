<template>
  <div class="cat-facts">
    <ul>
      <li>
        Name: <b>{{ catName }}</b>
      </li>
      <li>Has 4 Legs</li>
      <li>Makes a 'meow' sound</li>
      <li v-if="catName === 'Sicily'">Tries to eat spaghettios</li>
      <li v-else>Doesn't eat spaghettios</li>
      <li v-if="catName === 'Sicily'">Sleeps on tables</li>
      <li v-else>Sleeps in normal places</li>
      <li v-if="catName === 'Bella'">Is a calico cat</li>
      <li v-if="catName === 'Sicily'">Is a tuxedo cat</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CatFacts",
  props: {
    catName: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  width: fit-content;
  margin: auto;
}
li {
  text-align: left;
  margin: 6px 0;
  font-family: "Oswald", sans-serif;
  font-size: 18px;
}
</style>
