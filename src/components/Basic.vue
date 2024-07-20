<script setup>
  const props = defineProps({
    slotData: Object,
    updateSlot: Function
  })
  console.log("props.slotData",props.slotData)
</script>

<template>
  <button @click="updateSlot('okela')">
    <slot name="default"></slot>
  </button>
  <button>
    <slot name="one"/>
  </button>
</template>


<style scoped>

</style>