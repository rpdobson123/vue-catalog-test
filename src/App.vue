<template>
  <div id="app">
    <CatSelection />
    <WelcomeScreen msg="Select a cat to learn more" />
  </div>
</template>

<script>
import WelcomeScreen from "./components/WelcomeScreen.vue";
import CatSelection from "./components/CatSelection.vue";

export default {
  name: "App",
  components: {
    CatSelection,
    WelcomeScreen,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
