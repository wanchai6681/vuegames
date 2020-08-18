<template>
  <div>
    <button @click="counter">{}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
 
  data: function() {
    return {
      Counter: 0,
    };
  }
};
</script>

<style>
</style>
