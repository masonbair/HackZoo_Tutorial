<template>
  <img @click="state.count += 1" :src="image" />
  <p>Pets received: {{ state.count }}</p>
</template>

<script setup>
defineProps(["image"]);
const state = reactive({
  count: 0,
});
</script>
