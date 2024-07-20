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
  <!--  <Car :carData="carData"/>-->
  <!--  <Basic :slotData="data"-->
  <!--  :updateSlot="updateSlot"-->
  <!--  >Slot Button-->

  <!--  </Basic>-->
  <!--  <Basic :updateSlot="updateSlot">-->
  <!--    <template v-slot:default >-->
  <!--      <div >Slot Button default</div>-->
  <!--    </template>-->
  <!--    <template v-slot:one>-->
  <!--      <div >Slot Button 2</div>-->
  <!--    </template>-->
  <!--  </Basic>-->

  <div class="container">
    <button @click="activeComp = Mike">Mike</button>
    <button @click="activeComp = Steve">Steve</button>
<!--    <Mike v-if="activeComp === 'Mike'"/>-->
<!--    <Steve v-if="activeComp === 'Steve'"/>-->
    <keep-alive>
      <component :is="activeComp"></component>
    </keep-alive>
  </div>

</template>

<script setup>
import {provide, reactive, ref, shallowRef} from "vue";
import UserProfile from "./components/User/profile.vue"
import Car from "@/components/Car/car.vue";
import Basic from "@/components/Basic.vue";
import Steve from "@/components/Player/steve.vue";
import Mike from "@/components/Player/mike.vue";
const activeComp = shallowRef(Mike);

const data = reactive({
  name: "Francis",
  job: "Developer",
  age: 25,
  parents: {
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
  console.log("Updating Name", data)
  data.name = value;
}


const updateAge = (value) => {
  data.age = value;
}

const updateSlot = (value) => {
  console.log("Updating Slot")
  carData[0].brand = value;
}

const handleUpdateBrand = (value) => {
  console.log("Updating Brand", value)
  carData[0].brand = "value";
}

provide('carDataProvide', {
  carData,
  handleUpdateBrand
})

</script>

<style>

</style>
