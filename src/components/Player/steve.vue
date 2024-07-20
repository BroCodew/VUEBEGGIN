<script setup>
import {onUnmounted} from "vue";
import Modal from "@/Utils/modal.vue";

onUnmounted(() => {
  console.log("Steve is unmounted")

})
</script>

<template>
  <h1>Steve is on </h1>
  <Modal/>


</template>

<style scoped>

</style>