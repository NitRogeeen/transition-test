<template>
  <div class="app-contents">
    <random-move-box bg-color="cyan" opacity="0.8"/>
    <random-move-box bg-color="magenta" opacity="0.8"/>
    <random-move-box bg-color="yellow" opacity="0.8"/>
    <random-move-box bg-color="red" opacity="0.8"/>
    <random-move-box bg-color="green" opacity="0.8"/>
    <random-move-box bg-color="blue" opacity="0.8"/>
    <random-move-box bg-color="cyan" opacity="0.8"/>
    <random-move-box bg-color="magenta" opacity="0.8"/>
    <random-move-box bg-color="yellow" opacity="0.8"/>
    <random-move-box bg-color="red" opacity="0.8"/>
    <random-move-box bg-color="green" opacity="0.8"/>
    <random-move-box bg-color="blue" opacity="0.8"/>
  </div>
</template>

<script>
import RandomMoveBox from "./components/RandomMoveBox";

export default {
  name: "AppContents",
  components: {
    RandomMoveBox
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
