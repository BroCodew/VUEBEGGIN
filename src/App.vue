<template>
  <app-header/>
<!--  <UserProfile-->
<!--  :name="data.name"-->
<!--  lastName="Doe"-->
<!--  :age="data.age"-->
<!--  :parents="data.parents"-->
<!--  :updateAge="updateAge"-->
<!--  @update-name="updateName"-->
<!--  />-->
<!--  <button @click="updateName">Update Name</button>-->
  <Car :carData="carData"/>
</template>

<script setup>
import {provide, reactive, ref} from "vue";
import UserProfile from "./components/User/profile.vue"
import Car from "@/components/Car/car.vue";
const data = reactive({
  name: "Francis",
  job: "Developer",
  age: 25,
  parents:{
    father: "John",
    mother: "Jane"
  }
})

const carData = reactive([
  {
    brand: "Toyota",
    model: "Corolla",
    year: 2020
  },
  {
    brand: "Honda",
    model: "Civic",
    year: 2019
  },
  {
    brand: "Ford",
    model: "Fiesta",
    year: 2018
  }
])

const updateName = (value) => {
  console.log("Updating Name",data)
  data.name = value;
}


const updateAge = (value) => {
data.age = value;
}

const handleUpdateBrand = (value) => {
  console.log("Updating Brand", value)
  carData[0].brand = "test";
}

provide('carDataProvide', {
  carData,
  handleUpdateBrand
})

</script>

<style>

</style>
