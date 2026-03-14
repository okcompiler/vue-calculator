<script setup lang="ts">
import type { Operator } from '../types'

const emit = defineEmits<{
  number: [value: string]
  operator: [value: Operator]
  equals: []
  clear: []
  backspace: []
}>()

const numBtnClass = "dark:bg-gray-700 dark:border-gray-600 dark:text-white dark:hover:bg-gray-600 p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-100 hover:bg-gray-200";
const opBtnClass = "dark:bg-blue-700 dark:border-blue-600 dark:text-white dark:hover:bg-blue-600 p-4 text-xl cursor-pointer rounded border border-gray-300 bg-gray-400 hover:bg-gray-500";
const equalsBtnClass = "dark:bg-yellow-500 dark:text-white p-4 text-xl cursor-pointer rounded border border-yellow-500 bg-yellow-400 hover:bg-yellow-500 text-white";
</script>

<template>
  <div class="grid grid-cols-4 gap-2">
    <button @click="emit('clear')"
      class="p-4 text-xl cursor-pointer rounded border col-span-2 bg-red-500 text-white border-red-500 hover:bg-red-600">C</button>
    <button @click="emit('backspace')"
      class="dark:border-white col-span-2 p-4 text-xl cursor-pointer rounded bg-gray-500 text-white border border-black hover:bg-gray-600">⌫</button>
    <button @click="emit('number', '7')" :class="numBtnClass">7</button>
    <button @click="emit('number', '8')" :class="numBtnClass">8</button>
    <button @click="emit('number', '9')" :class="numBtnClass">9</button>
    <button @click="emit('operator', '/')" :class="opBtnClass">/</button>

    <button @click="emit('number', '4')" :class="numBtnClass">4</button>
    <button @click="emit('number', '5')" :class="numBtnClass">5</button>
    <button @click="emit('number', '6')" :class="numBtnClass">6</button>
    <button @click="emit('operator', '*')" :class="opBtnClass">*</button>

    <button @click="emit('number', '1')" :class="numBtnClass">1</button>
    <button @click="emit('number', '2')" :class="numBtnClass">2</button>
    <button @click="emit('number', '3')" :class="numBtnClass">3</button>
    <button @click="emit('operator', '-')" :class="opBtnClass">-</button>

    <button @click="emit('number', '0')" :class="numBtnClass">0</button>
    <button @click="emit('number', '.')" :class="numBtnClass">.</button>
    <button @click="emit('equals')" :class="equalsBtnClass">=</button>
    <button @click="emit('operator', '+')" :class="opBtnClass">+</button>
  </div>
</template>
