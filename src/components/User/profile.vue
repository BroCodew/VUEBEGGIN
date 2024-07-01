<template>
  <div>
    <h1>User Profile : {{name}}</h1>
    <p>{{lastName}}</p>
    <p>{{age}}</p>
    <p>{{parents.father}}</p>
    <div v-for="(value,key,index) in parents">
        {{key}} : {{value}}
    </div>
    <button @click="$emit('update-name')">
      Update Name By Child
    </button>
    <button @click="handleChangeLastName">
      Update Name By Child
    </button>
    <button @click="updateAge(30)">
      Update Age By Child
    </button>
  </div>
</template>

<script setup>
const emit = defineEmits(['update-name'])

const handleChangeLastName = () => {
  emit('update-name', "thai an")
}

const props = defineProps({
  name: {
    required:true,
    type: String,
    default:"N/A"
  },
  lastName: {
    type: String,
    validator: value => value === "Doe"
  },
  age: [Number,String],
  updateAge: Function,
  parents: Object
});

</script>


