<script setup lang="ts">
import Index from "./views/addToys.vue";
import NavBar from "./views/navBar.vue";
</script>

<template>
  <div class="flex flex-row">
    <NavBar id="navBar" />

    <div class="flex flex-col w-screen h-screen">
      <Index id="index " />
    </div>
  </div>
</template>

<style scoped>
#navBar {
  background-color: grey;
}

#index {
  background-color: aqua;
}
</style>
