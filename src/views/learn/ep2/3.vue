<script setup>
import { ref } from "vue";

const isCheck = ref(false);
const toggleCheck = () => {
  isCheck.value = !isCheck.value
}

const answer = ref('')
</script>

<template>
  <div>
    <!-- v-if v-else -->
    <!-- <div v-if="isCheck">
      แสดงคำนี้ออกมา
    </div>
    <div v-else>
      หายตัว
    </div>
    <button @click="toggleCheck">click to open</button> -->
    
    <!-- v-if-else else -->
     <div v-if="answer ==='Yes'">
      Answer is Yes
     </div>
     <div v-else-if="answer === 'No'">
      Answer is No
     </div>
     <div v-else>
      Plase select answer
     </div>
    <input type="radio" name="answer" value="Yes" v-model="answer">YES
    <input type="radio" name="answer" value="No" v-model="answer">NO
  </div>
</template>