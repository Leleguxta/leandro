<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  if(contador.value < 1000){
  contador.value++
  }
}
function decrementarContador() {
  if (contador.value > 0){
    contador.value--
  }
}
function reset(){
 contador.value = 0
} 

onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})
</script>

<template>
  <button @click="incrementarContador">+</button>
  <button @click="decrementarContador">-</button>
  <button @click="reset">/</button>
  <p>Valor do contador é: {{ contador }}</p>
</template>

<style scoped>
button {
  font-weight: bold;
  width: 80px;
  height: 80px;
  background-color: black;
  color: white;
  font-size: 50px;
  border: none;
  border-radius: 15%;
  margin-left: 20px;
  margin-bottom: 20px;
}
</style>
