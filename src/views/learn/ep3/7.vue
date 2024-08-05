<script setup>
// import Form from "./components/Form.vue";
import Counter from "./components/Counter.vue";
import { ref, onMounted } from "vue";

const message = ref('')

const changeMessage = (newMessage) => {
  message.value = newMessage
}
onMounted( () => {
  console.log('onMounted App.vue');
})
</script>
<template>
  <input type="text" v-model="message">
  <Counter :msg="message" :msgFunction="changeMessage"/>
  <!-- <Form /> -->
</template>