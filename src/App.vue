<script setup lang="ts">
import Display from './components/Display.vue'
import ButtonGrid from './components/ButtonGrid.vue'
import { ref } from 'vue'
import type { Operator } from './types'

const display = ref('0')
const firstNumber = ref('')
const operator = ref<Operator>('')

function handleNumber(num: string): void {
  if (num === '.' && display.value.includes('.')) return
  if (display.value === '0') {
    display.value = num
  } else {
    display.value += num
  }
}

function handleOperator(op: Operator): void {
  firstNumber.value = display.value
  operator.value = op
  display.value = '0'
}

function handleEquals(): void {
  const a = parseFloat(firstNumber.value)
  const b = parseFloat(display.value)
  let result = 0

  if (operator.value === '+') result = a + b
  else if (operator.value === '-') result = a - b
  else if (operator.value === '*') result = a * b
  else if (operator.value === '/') {
    if (b === 0) {
      display.value = 'Error'
      firstNumber.value = ''
      operator.value = ''
      return
    }
    result = a / b
  } else return

  display.value = String(result)
  firstNumber.value = ''
  operator.value = ''
}

function handleClear(): void {
  display.value = '0'
  firstNumber.value = ''
  operator.value = ''
}

function handleBackspace(): void {
  if (display.value.length === 1) {
    display.value = '0'
  } else {
    display.value = display.value.slice(0, -1)
  }
}
</script>

<template>
  <div class="w-72 mx-auto mt-24 border border-gray-300 p-5 rounded-lg">
    <Display :value="display" />
    <ButtonGrid @number="handleNumber" @operator="handleOperator" @equals="handleEquals" @clear="handleClear"
      @backspace="handleBackspace" />
  </div>
</template>
