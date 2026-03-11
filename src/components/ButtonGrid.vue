<script setup lang="ts">
import type { Operator } from '../types'

const emit = defineEmits<{
  number: [value: string]
  operator: [value: Operator]
  equals: []
  clear: []
  backspace: []
}>()
</script>

<template>
  <div class="grid grid-cols-4 gap-2">
    <button @click="emit('clear')"
      class="p-4 text-xl cursor-pointer rounded border col-span-2 bg-red-500 text-white border-red-500 hover:bg-red-600">C</button>
    <button @click="emit('backspace')"
      class="col-span-2 p-4 text-xl cursor-pointer rounded border bg-gray-500 text-white border-gray-500 hover:bg-gray-600">⌫</button>
    <button @click="emit('number', '7')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">7</button>
    <button @click="emit('number', '8')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">8</button>
    <button @click="emit('number', '9')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">9</button>
    <button @click="emit('operator', '/')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">/</button>

    <button @click="emit('number', '4')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">4</button>
    <button @click="emit('number', '5')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">5</button>
    <button @click="emit('number', '6')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">6</button>
    <button @click="emit('operator', '*')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">*</button>

    <button @click="emit('number', '1')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">1</button>
    <button @click="emit('number', '2')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">2</button>
    <button @click="emit('number', '3')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">3</button>
    <button @click="emit('operator', '-')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">-</button>

    <button @click="emit('number', '0')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">0</button>
    <button @click="emit('number', '.')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">.</button>
    <button @click="emit('equals')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">=</button>
    <button @click="emit('operator', '+')"
      class="p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200">+</button>
  </div>
</template>
