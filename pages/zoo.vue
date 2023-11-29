<template>
  <Animal v-for="animal in animals" :image="/animal" />
</template>

<script setup>
const animals = ref([]);
async function getAnimals(){
  const response = await $fetch("/api/loadzoo");
  animals.value = response;
}
onMounted(getAnimals);
</script>
