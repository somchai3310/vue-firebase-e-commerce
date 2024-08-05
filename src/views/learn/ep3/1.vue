<script setup>
import { ref, computed } from 'vue';  

const firstname  = ref('')
const lastname  = ref('')

// 
const fullname = computed(() =>{
  return `${firstname.value} ${lastname.value}`
})

// แบบ method จะไม่รู้ว่าค่าข้างในเปลี่ยนแปลงไปรึป่าว
const newFullname = () => {
  return `${firstname.value} ${lastname.value}`
}

</script>

<template>
  <div>
    Name: {{ firstname }} {{ lastname }}
  </div>
  <div>
    FullName: {{ fullname }}
  </div>
  <div>
    newFUllname: {{ newFullname }}
  </div>
  <div>
    Firstname <input type="text" v-model="firstname">
    lastname <input type="text" v-model="lastname">
  </div>
</template>