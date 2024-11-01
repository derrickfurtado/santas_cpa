<script setup lang="ts">

import { ref } from 'vue';

const newGoal = ref<string>(''); // Bind to the input field
const goals = ref<string[]>([]); // Array to hold all the goals

// Function to add a new goal to the list
function addGoal() {
  if (newGoal.value.trim()) {
    goals.value.push(newGoal.value);
    newGoal.value = ''; // Clear the input field
  }
}

</script>

<template>

    <div id="app" class="flex flex-col p-4">
        <div class="flex items-center space-x-2 mb-4">
            <label for="goal" class="text-3xl font-bold">Goal:</label>
            <input 
                type="text" 
                id="goal" 
                class="input input-bordered"
                v-model="newGoal"
                placeholder="Enter your goal here"
            />
            <button @click="addGoal" class="btn">Add Goal</button>
        </div>
        <div class="flex flex-col">
            <ul>
                <li 
                    v-for="(goal,index) in goals" 
                    :key="index"
                    class="mb-1 p-2 bordered rounded"
                >
                    {{ goal }}
                </li>
            </ul>
        </div>
    </div>

</template>


<style scoped></style>