<template>
  <div class="editor-wrapper">
    <Editor v-bind="attrs" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Editor from './Editor.vue'

export default defineComponent({
  components: {
    Editor,
  },
  computed: {
    attrs() {
      return {
        ...this.$attrs,
        'onUpdate:modelValue'(...args: any[]) {
          console.log('Options API: onUpdateModelValue', ...args)
        },
      }
    },
  },
})
</script>

<style lang="postcss" scoped>
.editor-wrapper {
  border: solid 2px gray;
  border-radius: 2px;
  padding: 5px;
}
</style>
