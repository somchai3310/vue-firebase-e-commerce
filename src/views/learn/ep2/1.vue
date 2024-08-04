<script setup>
import {ref} from  'vue' // ใช้แทนกันได้ทั้งสอง
import { reactive } from 'vue' //ใช้กับ obj ใหญ่ๆ ดีกว่า ไม่ต้องใช้ .value

const counter = ref(0)
const counterObj = reactive({count:0})
const searchText = ref('typing')

const increase = ()=>{
  counter.value = counter.value+1
}
const increaseObj = ()=>{
  counterObj.count = counterObj.count+1
}

</script>

<template>
  <div>
    Counter {{ counter }}
    <button @click="increase">Add counter</button>
    CounterObj {{ counterObj.count }}
    <button @click="increaseObj">Add counterObj</button>
    <div>{{ searchText }}</div>
  <input v-model="searchText" />
  </div>
</template>
