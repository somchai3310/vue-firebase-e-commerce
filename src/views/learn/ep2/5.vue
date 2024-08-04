<script setup>
import { ref } from "vue";

const items = ref(["Item 1", "Item 2", "Item 3", "Item 4"]);
const addNewItme  = () => {
  const itemsLength = items.value.length+1
  items.value.push('item '+itemsLength)
}
</script>

<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item">{{ item }}</li>
    </ul>
    <button @click="addNewItme">add new item</button>
  </div>
</template>