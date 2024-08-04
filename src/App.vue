<script setup>
import { reactive } from "vue";

const formData = reactive({
  interest: []
})
const genderList = ["Male", "female", "other"];
const interestsList = ["book", "sport", "game"];

const summitForm = () =>{
  console.log('summit form');
  console.log('data',formData);
  console.log('interest',formData.interest);
}
</script>

<template>
  <div>
    <div>
      <div>firstname</div>
      <input type="text" name="firstname" v-model="formData.firstname"/>
    </div>
    <div>
      <div>lastname</div>
      <input type="text" name="lastname" v-model="formData.lastname"/>
    </div>
    <div>
      <div>Gender</div>
      <div v-for="gender in genderList" :key="gender">
        <input type="radio" name="gender" :value="gender" v-model="formData.gender" />{{ gender }}
      </div>
    </div>
    <div>
      <div>interests</div>
      <div v-for="interest in interestsList" :key="interest">
        <input type="checkbox" name="interests" :value="interest" v-model="formData.interest"/>{{
          interest
        }}
      </div>
    </div>
    <div>
      <div>Description</div>
      <textarea name="desc" id="" cols="30" rows="5" v-model="formData.description"></textarea>
    </div>
    <button @click="summitForm()">Send Form</button>
  </div>
</template>