<script setup>
  import { ref } from 'vue';

  const count = ref(0)
  count.value = 1
  count.value++

  const objectRef = ref({ count: 0 })
  objectRef.value = { count: 1 } // Isso funciona de forma reativa

</script>

<template>
  <!-- No template não é necessário utilizar .value -->
  <p>{{ count }}</p>
  <button @click="count++">Adicionar +1</button>

</template>

<!--
  Para lidar com as limitações do reactive() com tipos primitivos(string, numberou boolean),
  o Vue também fornece uma função ref() que nos permite criar "refs" reativas 
  que podem conter qualquer tipo de valor.
-->