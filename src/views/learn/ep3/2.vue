<script setup>
import { ref, computed } from "vue";

const priceUSD = ref(1);
const exchangeRate = 35;

const priceTHB = computed({
  get: () => {
    return priceUSD.value * exchangeRate;
  },
  set: (newValue) => {
    priceUSD.value = newValue / exchangeRate;
  },
});
</script>

<template>
  <div>USD {{ priceUSD }} THB {{ priceTHB }}</div>
  <div>
    <div>THB <input type="text" v-model="priceTHB" /></div>
    <div>USD <input type="text" v-model="priceUSD" /></div>
  </div>
</template>