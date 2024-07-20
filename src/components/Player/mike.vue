<script setup>
import {onUnmounted} from "vue";
import Modal from "@/Utils/modal.vue";

onUnmounted(()=>{
  console.log("Mike is unmounted")
})


</script>

<template>
<h1>Mike is on</h1>
  <Modal/>
</template>

<style scoped>

</style>