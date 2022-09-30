<script setup>
import { ref, nextTick } from 'vue'

const count = ref(0)

async function increment() {
  
  count.value++ // O estado do count foi alterado

  nextTick(() => {
    console.info(`Agora o DOM está atualizado: ${document.getElementById('counter').textContent}`)
  })

  console.info(`DOM ainda não foi atualizado: ${document.getElementById('counter').textContent}`)
}
</script>

<template>
  <p>count <span id="counter">{{ count }}</span>
  </p>

  <button @click="increment">Adicionar +1</button>
</template>