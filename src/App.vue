<script setup>
import { ref, onMounted } from 'vue'

const rawHtml = '<span style="color: red">Este é um texto em vermelho</span>'

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

const numero = 1
const ok = true
const mensagem = 'programar'
function inverter(texto) {
    return texto.split('').reverse().join('')
}
</script>

<template>
  <button @click="incrementarContador">+</button>
  <button @click="decrementarContador">-</button>
  <button @click="reset">/</button>
  <p>Valor do contador é: {{ contador }}</p>
  <p>Usando interpolação de textos: {{rawHtml}}</p>
  <p>Usando v-html: <span v-html="rawHtml"></span></p>
  <p>{{ numero + 1 }}</p>
  <p>{{ ok ? 'Sim' : 'Não' }}</p>
  <p>{{ mensagem.split('').reverse().join('') }}</p>
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
