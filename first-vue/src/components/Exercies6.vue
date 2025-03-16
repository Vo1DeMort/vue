<script setup>
import { ref } from 'vue';

//NOTE: what a shit language
// const values for variables and yet still changeable
const totalCost = ref(0);
const totalItems = ref(0);

const addToCart = (n) => {
  totalItems += 1;
  totalCost += 1;
}


//FIX: this doesn't work yet
</script>

<template>
  <div>
    <h1>Returning methods</h1>
    <div>Cart ({{ totalItems }}) {{ totalCost }}</div>
    <ul>
      <li v-for="n in 5" :key="n">
        <button @click="addToCart(n)">
          add {{ n }}
        </button>
      </li>
    </ul>
  </div>
</template>
