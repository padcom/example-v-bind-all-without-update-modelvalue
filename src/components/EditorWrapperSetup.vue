<template>
  <div class="editor-wrapper">
    <Editor v-bind="attrs" />
  </div>
</template>

<script lang="ts" setup>
import { computed, useAttrs } from 'vue'
import Editor from './Editor.vue'

const attrs = computed(() => ({
  ...useAttrs(),
  'onUpdate:modelValue'(...args: any[]) {
    console.log('Setup API: onUpdateModelValue', ...args)
  },
}))
</script>

<style lang="postcss" scoped>
.editor-wrapper {
  border: solid 2px gray;
  border-radius: 2px;
  padding: 5px;
}
</style>
