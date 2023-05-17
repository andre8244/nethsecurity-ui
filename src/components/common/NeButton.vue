<script setup lang="ts">
import { computed, type PropType } from 'vue'

type ButtonKind = 'primary' | 'secondary' | 'tertiary' | 'danger'
type ButtonSize = 'xs' | 'sm' | 'md' | 'lg' | 'xl'

defineProps({
  kind: {
    type: String as PropType<ButtonKind>,
    default: 'secondary'
  },
  size: {
    type: String as PropType<ButtonSize>,
    default: 'md'
  }
})

const baseStyle = 'font-semibold shadow-sm'
const sizeStyle = {
  xs: 'rounded px-2 py-1 text-xs',
  sm: 'rounded px-2 py-1 text-sm',
  md: 'rounded-md px-2.5 py-1.5 text-sm',
  lg: 'rounded-md px-3 py-2 text-sm',
  xl: 'rounded-md px-3.5 py-2.5 text-sm'
}
const kindStyle = {
  primary:
    'bg-indigo-600 text-white hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600',
  secondary: 'bg-white text-gray-900 ring-1 ring-inset ring-gray-300 hover:bg-gray-50'
}

//// fix
const allStyles = computed(() => baseStyle + ' ' + kindStyle['secondary'] + ' ' + sizeStyle['md'])
</script>

<template>
  <button :class="allStyles"><slot></slot></button>
</template>

<!-- //// remove? -->
<style scoped></style>
