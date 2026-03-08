<script setup lang="ts">
const props = defineProps<{ value: string }>()
</script>

<template>
<div class="display">{{ value }}</div>
</template>

<style scoped>
.display {
  background: #222;
  color: white;
  text-align: right;
  padding: 10px;
  font-size: 2em;
  border-radius: 4px;
  margin-bottom: 10px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
</style>
