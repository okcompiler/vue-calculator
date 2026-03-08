<script setup lang="ts">
import Display from './components/Display.vue'
import ButtonGrid from './components/ButtonGrid.vue'
import { ref } from 'vue'

const display = ref('0')
const firstNumber = ref('')
const operator = ref('')

function handleNumber(num: string) {
  if (num === '.' && display.value.includes('.')) return
  if (display.value === '0') {
    display.value = num
  } else {
    display.value += num
  }
}

function handleOperator(op: string) {
  firstNumber.value = display.value
  operator.value = op
  display.value = '0'
}

function handleEquals() {
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

function handleClear() {
  display.value = '0'
  firstNumber.value = ''
  operator.value = ''
}

function handleBackspace() {
  if (display.value.length === 1) {
    display.value = '0'
  } else {
    display.value = display.value.slice(0, -1)
  }
}
</script>

<template>
  <div class="calculator">
    <Display :value="display" />
    <ButtonGrid
      @number="handleNumber"
      @operator="handleOperator"
      @equals="handleEquals"
      @clear="handleClear"
      @backspace="handleBackspace"
    />
  </div>
</template>

<style scoped>
.calculator {
  width: 300px;
  margin: 100px auto;
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 8px;
}
</style>
