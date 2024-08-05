<script setup>
// defineProps -> รับ props
import { ref, defineProps, onMounted } from 'vue';

const count = ref(0)
const msg = ref('')

const increaseCounter = () => {
  count.value +=1
}
defineProps({
  msg: String,
  msgFunction: Function
})
onMounted(() => {
  console.log('onMounted Counter.vue');
})
</script>

<template>
  <div>Hello {{ msg }}</div>
  <div>
    <input type="text" v-model="msg">
    <button @click="msgFunction(msg)">Change message from Counter</button>
  </div>
  <button @click="increaseCounter">Click {{ count }}</button>
</template>