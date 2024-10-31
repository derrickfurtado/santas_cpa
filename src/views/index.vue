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



// const funcLogic = createApp({
//   data() {
//     return {
//       goals: [],
//       enteredValue: ''
//     };
//   },
//   methods: {
//     addGoal() {
//       this.goals.push(this.enteredValue);
//     }
//   }
// });


</script>

<template>
    <div>
        <div id="app" class="flex flex-col">
            <div class="flex">
                <label for="goal">
                    <span class="text-2xl">Goal</span>
                </label>
                <input type="text" id="goal" v-model="newGoal" />
                <button @click="addGoal" class="btn">Add Goal</button>
            </div>
            <div class="flex flex-col">
                <ul>
                    <li v-for="(goal,index) in goals" :key="index">
                        {{ goal }}
                    </li>
                </ul>
            </div>
        </div>
    </div>




</template>

<style scoped></style>