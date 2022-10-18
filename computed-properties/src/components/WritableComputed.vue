<script setup>
import { ref, computed } from 'vue'

const firstName = ref('Geverson')
const lastName = ref('Loch')

const fullName = computed({ // Repare que desta vez é passado um objeto e não uma função!
  get() { // Getter
    return `${firstName.value} ${lastName.value}`
  },
  set(newName) { // Setter
    [firstName.value, lastName.value] = newName.split(' ')
    // Nota: estamos usando a sintaxe de atribuição de desestruturação aqui.
  }
})
</script>

<template>
  <p>Meu nome é: {{ firstName }}</p>
  <p>Meu sobrenome é: {{ lastName }}</p>
  <p>Meu nome completo é: {{ fullName }}</p>
  <input type="text" v-model="fullName">
  <button @click="fullName = 'John Doe'">Alterar nome: John Doe</button>
</template>