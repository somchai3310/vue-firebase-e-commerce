<!-- watcher -->
<script setup>
import { ref, computed, watch } from "vue";

const fullname = ref("");
const upperFullnameWatch = ref("");

const firstname = ref("");
const lastname = ref("");
const fullname2 = ref("");

const upperFullname = computed(() => {
  return fullname.value.toUpperCase();
});

watch(fullname, (newFullname, oldFullname) => {
  upperFullnameWatch.value = newFullname.toUpperCase();
  console.log("newFUllname", newFullname);
  console.log("oldFullname", oldFullname);
});

watch([firstname, lastname], (newFullname, oldFullname) => {
  fullname2.value = `${newFullname[0]} ${newFullname[1]}`;
  console.log("newfullname f l", newFullname);
});
</script>

<template>
  <div>
    <div>Fullname: {{ upperFullname }}</div>
    <div>Fullname watch: {{ upperFullnameWatch }}</div>
    <div>fullname : <input type="text" v-model="fullname" /></div>
    <hr />
    <div>Firstname : <input type="text" v-model="firstname" /></div>
    <div>Lastname : <input type="text" v-model="lastname" /></div>
    <br />
    {{ fullname2 }}
  </div>
</template>