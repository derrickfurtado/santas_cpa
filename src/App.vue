<script setup lang="ts">
import Index from "./views/addToys.vue";
import NavBar from "./views/navBar.vue";
</script>

<template>
  <div class="flex flex-row w-screen">
    <NavBar id="navBar" class="flex flex-col h-screen max-w-[15%]"/>

    <Index id="index" class="w-screen h-auto"/>
  </div>
</template>

<style scoped>
#navBar {
  background-color: grey;
}

#index {
  background-color: rgb(143, 216, 216);
}
</style>
