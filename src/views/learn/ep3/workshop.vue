<!-- profile Form -->
<script setup>
import { ref, computed, onMounted, watch } from "vue";

const isLoading = ref(false);
const isUpdated = ref(false);
const isValid = ref(true);
const errors = ref({});

const firstname = ref("");
const lastname = ref("");
const email = ref("");

const fullname = computed(() => {
  // console.log("computed");
  return `${firstname.value} ${lastname.value}`;
});

const updateProfile = async () => {
  isLoading.value = true;
  // จำลอง การส่ง API ออกมา
  await new Promise((resolve) => setTimeout(resolve, 2000));
  isLoading.value = false;
  isUpdated.value = true;
};

const validateName = name => {
  // มีตัวเลข
  const re = /\d/
  return !re.test(name)
}

const validateEmail = (email) => {
  return email.includes('@')
}

watch([firstname, lastname, email], () => {
  isValid.value = true
  isUpdated.value = false
  errors.value = {}

  if(!validateName(firstname.value)){
    isValid.value = false
    errors.value.firstname = 'ชื่อไม่ถูกต้อง'
  }
  if(!validateName(lastname.value)){
    isValid.value = false
    errors.value.lastname = 'นามสกุลไม่ถูกต้อง'
  }
  if(!validateEmail(email.value)){
    isValid.value = false
    errors.value.email = 'อีเมล์ไม่ถูกต้อง'
  }
})

onMounted(() => {
  // console.log("onMounted");
  firstname.value = "somchai";
  lastname.value = "mustofa";
  email.value = "ss@gg.com";
});
</script>

<template>
  <div class="container">
    <div>
      <div>Fullname: {{ fullname }}</div>
      <div>Email: {{ email }}</div>
    </div>
    <div>
      <div>Firstname</div>
      <input type="text" v-model="firstname" />
      <div class="error-text">{{ errors.firstname }}</div>
    </div>
    <div>
      <div>Lastname</div>
      <input type="text" v-model="lastname" />
      <div class="error-text">{{ errors.lastname }}</div>
    </div>
    <div>
      <div>Email</div>
      <input type="email" v-model="email" />
      <div class="error-text">{{ errors.email }}</div>
    </div>
    <div v-if="isLoading" class="loading">Loading...</div>
    <button class="button" @click="updateProfile()" :disabled="!isValid">
      Upadte Profile
    </button>
    <div v-if="isUpdated" class="loading">Profile Updated!</div>
  </div>
</template>
<style>
.error-text{
  color: red;
  font-size: small;
  text-align: right;
}
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  max-width: 320px;
  margin: 0 auto;
}

.container > div {
  width: 100%;
}

.button {
  width: 100%;
  height: 26px;
  margin-top: 20px;
}
.loading {
  background-color: #fff;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  margin: 10px 0;
}
input {
  width: 100%;
}
</style>