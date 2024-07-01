<template>

  <List :carData="carData"/>
  <Footer/>
</template>

<script setup>
import Footer from "@/components/header_footer/footer.vue";
import List from "@/components/Car/list.vue";

// const props = defineProps(["carData"]);

const props = defineProps({
  carData: Array
})

</script>


<style scoped>

</style>

