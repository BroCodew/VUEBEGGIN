<template>
  <div v-for="item in carData">
    {{item.brand}} - {{item.model}} - {{item.year}}
  </div>
  <button @click="handleUpdateBrand">Change Brand</button>
</template>

<script setup>

// const props = defineProps({
//   carData: Array
// })

import {inject} from "vue";

const {carData, handleUpdateBrand} = inject('carDataProvide')

</script>


<style scoped>

</style>