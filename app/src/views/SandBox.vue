<script setup lang="ts">
import BaseTextInput from '@/components/BaseTextInput.vue'
import { ref } from 'vue'
const firstName = ref('')
</script>

<template>
  {{ firstName }}
  <div>
    <BaseTextInput id="task-title" label="hero" v-model="firstName" />
  </div>
</template>

<style scoped></style>
