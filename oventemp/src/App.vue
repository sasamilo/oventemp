<script setup>
import { ref } from 'vue'

const c = ref(0)
const f = ref(32)

function setC(e, v = +e.target.value) {
  c.value = v
  f.value = v * (9 / 5) + 32
}

function setF(e, v = +e.target.value) {
  f.value = v
  c.value = (v - 32) * (5 / 9)
}
</script>

<template>
<container>
  <input class="box" type="number" :value="f" @change="setF"> Fahrenheit =
  <input class="box" type="number" :value="c" @change="setC"> Celsius
  </container>
</template>

<style>
container {
  height: 15vh;
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-direction: column;
  font-family: sans-serif;
}

.box {
  border-radius: 2em;
  border-color: none;
}
</style>