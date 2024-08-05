<script setup>
// import Form from "./components/Form.vue";
import Counter from "./components/Counter.vue";
import { ref } from "vue";

const message = ref('')

const changeMessage = (newMessage) => {
  message.value = newMessage
}
</script>
<template>
  <input type="text" v-model="message">
  <Counter :msg="message" :msgFunction="changeMessage"/>
  <!-- <Form /> -->
</template>