<template>
  <app-header/>
  <UserProfile
  :name="data.name"
  lastName="Doe"
  :parents="data.parents"
  />
  <button @click="updateName">Update Name</button>
  <Footer />
</template>

<script setup>
import {reactive, ref} from "vue";
import Footer from "./components/header_footer/footer.vue";
import UserProfile from "./components/User/profile.vue"
const data = reactive({
  name: "Francis",
  job: "Developer",
  parents:{
    father: "John",
    mother: "Jane"
  }
})

const updateName = () => {
  console.log("Updating Name",data)
  data.name = "John";
}

</script>

<style>

</style>
