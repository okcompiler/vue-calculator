<script setup lang="ts">
const emit = defineEmits<{
  number: [value: string]
  operator: [value: string]
  equals: []
  clear: []
  backspace: []
}>()
</script>

<template>
<div class="buttons">
  <button @click="emit('clear')" class="clear">C</button>
  <button @click="emit('backspace')" class="backspace">⌫</button>
  <button @click="emit('number', '7')">7</button>
  <button @click="emit('number', '8')">8</button>
  <button @click="emit('number', '9')">9</button>
  <button @click="emit('operator', '/')">/</button>

  <button @click="emit('number', '4')">4</button>
  <button @click="emit('number', '5')">5</button>
  <button @click="emit('number', '6')">6</button>
  <button @click="emit('operator', '*')">*</button>

  <button @click="emit('number', '1')">1</button>
  <button @click="emit('number', '2')">2</button>
  <button @click="emit('number', '3')">3</button>
  <button @click="emit('operator', '-')">-</button>

  <button @click="emit('number', '0')">0</button>
  <button @click="emit('number', '.')">.</button>
  <button @click="emit('equals')">=</button>
  <button @click="emit('operator', '+')">+</button>
</div>
</template>

<style scoped>
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 8px;
}

button {
  color: #000;
  padding: 15px;
  font-size: 1.2em;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 4px;
  background: #f9f9f9;
}

button.clear {
  grid-column: span 2;
  background: #ff4444;
  color: white;
  border-color: #ff4444;
}

button.backspace {
  grid-column: span 2;
  background: gray;
  color: white;
  border-color: #aaa;
}

button:hover {
  background: #e0e0e0;
}

</style>
