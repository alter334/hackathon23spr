<script setup lang="ts">
import FizCt from './FizzBuzzCounter.vue'
defineProps<{
  msg: string
}>()
</script>

<template>
  <div>
    <FizCt />
  </div>
</template>

<style></style>
