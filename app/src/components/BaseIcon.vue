<script lang="ts" setup>
import { Icon } from '@iconify/vue'
import { computed, defineAsyncComponent } from 'vue'

const props = defineProps({
  name: {
    required: true,
    type: String,
  },
  source: {
    type: String,
    default: 'iconify',
  },
  width: {
    type: Number,
    default: 20,
  },
  height: {
    type: Number,
    default: 20,
  },
})

const computeIcon = computed(() => {
  if (props.name !== 'iconify') {
    return defineAsyncComponent(() => import(`@/components/Icons/${props.name}.vue`))
  } else {
    return null
  }
})
</script>

<template>
  <Icon
    v-if="source === 'iconify'"
    :icon="props.name"
    :width="props.width"
    :height="props.height"
  />
  <component
    v-else
    :is="computeIcon"
    :icon="props.name"
    :width="props.width"
    :height="props.height"
  />
</template>
<style scoped></style>
