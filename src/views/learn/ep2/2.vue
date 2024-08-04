<script setup>
import { ref } from "vue";

const fullName = ref('')

const chageInput = (event) => {
  fullName.value = event.target.value
}
</script>

<template>
  <div>
    {{ fullName }}
    <input type="text" @input="chageInput">
    <input type="text" v-model="fullName">
  </div>
</template>



<style>

</style>