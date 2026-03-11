<script setup lang="ts">
defineProps<{ value: string }>()
</script>

<template>
  <div
    class="bg-gray-800 text-white text-right px-4 py-3 text-3xl rounded mb-3 overflow-hidden text-ellipsis whitespace-nowrap">
    {{ value }}
  </div>
</template>
