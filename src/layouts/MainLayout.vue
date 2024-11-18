<template>
  <div class="row q-mt-xl">
    <div class="col-2"></div>
    <div class="col" style="width: 200px;">
      <h3 class="text-center">Calculadora</h3>

      <q-input v-model="displayCalculator" readonly class="q-mb-md text-h5 text-center" outlined style="font-size: 24px" />

      <div class="flex justify-center">
        <q-btn class="q-ma-sm" size="20px" round color="orange" @click="clear">C</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('%')">%</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('(')">(</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('/')">÷</q-btn>
      </div>

      <div class="flex justify-center">
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('9')">9</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('8')">8</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('7')">7</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('*')">×</q-btn>
      </div>

      <div class="flex justify-center">
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('6')">6</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('5')">5</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('4')">4</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('-')">−</q-btn>
      </div>

      <div class="flex justify-center">
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('3')">3</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('2')">2</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('1')">1</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color=""/>
      </div>

      <div class="flex justify-center">
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('0')">0</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="green-4" @click="input('.')">.</q-btn>
        <q-btn class="q-ma-sm" size="20px" round color="secondary" @click="calculate('=')">=</q-btn>
        <q-btn class="q-ma-sm" size="20px" color="green-4" @click="input('+')">+</q-btn>
      </div>
    </div>
    <div class="col-2"></div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const displayCalculator = ref('')

const clear = () => {
  displayCalculator.value = ''
}

const input = (value) => {
  displayCalculator.value += value;
}

const calculate = () => {
    displayCalculator.value = String(eval(displayCalculator.value.replace('÷', '/').replace('×', '*')))


}




</script>
