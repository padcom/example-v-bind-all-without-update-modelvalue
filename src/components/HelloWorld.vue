<template>
  <h1>Hello, world! {{ message }}</h1>
  <EditorWrapperOptions v-model="text" />
  <EditorWrapperSetup v-model="text" />
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import EditorWrapperOptions from './EditorWrapperOptions.vue'
import EditorWrapperSetup from './EditorWrapperSetup.vue'

defineProps({
  message: { type: String, default: 'from HelloWorld.vue' },
})

const text = ref('change me')
</script>

<style lang="postcss" scoped>
h1 {
  font-size: 1.875rem;
  line-height: 2.25rem;
}
</style>
