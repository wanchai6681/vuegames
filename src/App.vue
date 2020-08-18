<template>
  <div id="App">
  <img v-bind:src="selectedImage" />
  <counter lable="Start"/>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Counter from "./components/Cunter";
export default {
  name: "App",
  components: {
    HelloWorld,
    Counter,
  },

  data: function () {
    return {
      images: [
      'img/alien-spaceship-flying-cosmos-planets_33099-2480.jpg',
      'img/c1_1764659_191004103525.jpg',
      'img/Infinity_Vol_1_4_Generals_Variant_Textless.jpg',
    ],
    selectedImage: ''
  },
  created () {
    const idx = Math.floor(Math.random() * this.images.length);
    this.selectedImage = this.images[idx]
  }
    
    }
  }
}
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