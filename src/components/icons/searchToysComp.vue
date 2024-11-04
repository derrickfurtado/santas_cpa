<script setup lang="ts">
import { ref } from "vue";

const newToy = ref<string>(""); // Bind to the input field
const toyBox = ref<string[]>([]); // Array to hold all the toys

// Function to add a new toy to the list
function addToy() {
  if (newToy.value.trim()) {
    toyBox.value.push(newToy.value);
    newToy.value = ""; // Clear the input field
  }
}
</script>

<template>
  <div id="searchAddToys" class="flex flex-col p-4 max-w-[30dvw]">
    <div class="flex flex-col items-center space-x-2 mb-4 p-4">
      <label for="toy" class="text-3xl font-bold m-2">Search for Toys:</label>
      <input
        type="text"
        id="toy"
        class="input input-bordered"
        v-model="newToy"
        placeholder="Place Toy Here"
      />
      <button @click="addToy" class="btn m-3">
        Send to Santa's Accountant
      </button>
    </div>
    <div class="flex flex-col items-center">
      <ul>
        <div class="toast toast-end">
          <div
            id="toyOnList"
            class="alert alert-info"
            v-for="(singleToy, index) in toyBox"
            :key="index"
          >
            {{ singleToy }}
          </div>
        </div>
      </ul>
    </div>
  </div>
</template>

<style scoped>
/* #searchAddToys {
  background: silver;
} */
</style>
