<template>
  <div class="calculator">
    <div v-for="num in numbers" :key="num" class="button" @click="showNumber(num)">
      {{ num }}
    </div>
    <p v-if="selectedNumber">Has clicat: {{ selectedNumber }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const selectedNumber = ref(null);

const showNumber = (num) => {
  selectedNumber.value = num;
};
</script>

<style>
.calculator {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  width: 200px;
  margin: auto;
}

.button {
  padding: 20px;
  background: lightgray;
  color: black;
  text-align: center;
  cursor: pointer;
  border-radius: 5px;
}
</style>
