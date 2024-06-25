<template>
  <div>
    <h1>User Profile : {{name}}</h1>
    <p>{{lastName}}</p>
    <p>{{parents.father}}</p>
    <div v-for="(value,key,index) in parents">
        {{key}} : {{value}}
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  lastName: String,
  parents: Object
});

</script>


