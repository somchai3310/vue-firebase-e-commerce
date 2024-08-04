<!-- 
v-if จะหายไปเลย
v-show แค่ซ่อนไว้ 
-->
<script setup>
import { ref } from 'vue'

const isChecked = ref(false)

</script>

<template>
  <div>
    <div>
      <input type="checkbox" v-model="isChecked">
      ติ๊กถูกเพื่อแสดงผล
    </div>
    <div v-show="isChecked">
      Checkbox is checked! (v-show)
    </div>
    <div v-if="isChecked">
      Checkbox is checked! (v-if)
    </div>
  </div>
</template>