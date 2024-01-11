<template>
  <label>Some input (current: {{ modelValue }})</label>
  <input v-model="value">
</template>

<script lang="ts" setup>
import { computed } from 'vue'

const props = defineProps({
  modelValue: { type: String, default: '' },
})

const emit = defineEmits([
  'update:modelValue',
])

const value = computed({
  get() {
    return props.modelValue
  },
  set(newValue: string) {
    emit('update:modelValue', newValue)
  },
})
</script>
