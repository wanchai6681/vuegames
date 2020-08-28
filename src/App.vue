<template>
  <div id="app">
    <HelloWorld msg="" />
    <wbutton></wbutton> />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Wbutton from "./components/Wbutton";

export default {
  name: "App",
  components: {
    HelloWorld,
    Wbutton,
  },
};
</script>

<style>
#app {
  background-size: cover;
  background-image: url(https://thestandard.co/wp-content/uploads/2020/07/THE-POWER-GAME-EP60-COVER-WEB-800x430.jpg);
  font-family: "Permanent Marker", cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #646464;
}
</style>
