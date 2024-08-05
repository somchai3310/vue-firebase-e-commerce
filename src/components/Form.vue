<!-- watcher -->
<script setup>
import { ref, reactive, watchEffect, watch } from "vue";

const formData = reactive({
  firstname: "",
  lastname: "",
});

const fullname = ref("");

// watch(
//   () => formData,
//   (newFullname, oldFullname) => {
//     fullname.value = `${newFullname.firstname} ${newFullname.lastname}`;
//   },
//   {deep: true}
// );

watchEffect(() => {
  console.log("formData from watchEffect", formData);
  fullname.value = `${formData.firstname} ${formData.lastname}`;
});

watch(
  formData,
  (newForm, oldForm) => {
    console.log("formData from watch", formData);
  },
  // จะเช็คค่าก่อน จนกว่าจะใส่ immediate
  { immediate: true }
);
</script>

<template>
  <div>
    {{ fullname }}
    <div>firstname : <input type="text" v-model="formData.firstname" /></div>
    <div>lastname : <input type="text" v-model="formData.lastname" /></div>
  </div>
</template>