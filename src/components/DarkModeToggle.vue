<script setup lang="ts">
defineProps<{ isDark: boolean }>()
const emit = defineEmits<{ toggle: [] }>()
</script>

<template>
  <div class="flex items-center justify-center gap-2 mb-3">
    <span class="text-sm text-gray-500 dark:text-gray-400">☀️</span>
    <button @click="emit('toggle')" class="relative w-12 h-6 rounded-full transition-colors duration-300"
      :class="isDark ? 'bg-blue-600' : 'bg-gray-300'">
      <span class="absolute top-1 left-1 w-4 h-4 bg-white rounded-full shadow transition-transform duration-300"
        :class="isDark ? 'translate-x-6' : 'translate-x-0'" </span>
    </button>
    <span class="text-sm text-gray-500 dark:text-gray-400">🌙</span>
  </div>
</template>
