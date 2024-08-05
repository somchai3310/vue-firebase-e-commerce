<!-- watcher -->
<script setup>
import { ref, reactive, watch } from "vue";

const formData = reactive({
  firstname: "",
  lastname: "",
});

const fullname = ref("");

// วิธีที่1
// watch(
//   () => [formData.firstname, formData.lastname],
//   (newFullname, oldFullname) => {
//     fullname.value = `${newFullname[0]} ${newFullname[1]}`;
//   }
// );

// วิธีที่2
// watch(
//   formData,
//   (newFullname, oldFullname) => {
//   fullname.value = `${newFullname.firstname} ${newFullname.lastname}`;
// });

// วิธีที่3
watch(
  () => formData,
  (newFullname, oldFullname) => {
    fullname.value = `${newFullname.firstname} ${newFullname.lastname}`;
  },
  {deep: true}
);


</script>

<template>
  <div>
    {{ fullname }}
    <div>firstname : <input type="text" v-model="formData.firstname" /></div>
    <div>lastname : <input type="text" v-model="formData.lastname" /></div>
  </div>
</template>