<script setup lang="ts">
defineOptions({
  inheritAttrs: false,
})
defineProps({
  id: {
    required: true,
    type: String,
  },
  label: {
    required: true,
    type: String,
  },
})

const textValue = defineModel<string>()
</script>

<template>
  <div class="form-control">
    <label class="label" :for="id">
      <span class="label-text font-medium">{{ label }} *</span>
    </label>
    <input
      :id="id"
      class="input input-bordered w-full"
      type="text"
      v-model="textValue"
      v-bind="$attrs"
    />
  </div>
</template>

<style scoped></style>
