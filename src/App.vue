<template>
  <div id="app">
    <app-contents/>
  </div>
</template>

<script>
import AppContents from "./AppContents";

export default {
  name: "App",
  components: {
    AppContents
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
