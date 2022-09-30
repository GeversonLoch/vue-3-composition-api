<script setup>
  import { $ref } from 'vue/macros'
  
  let count = $ref(0)
  count = 1
  count++

  const objectRef = ref({ count: 0 })
  objectRef.value = { count: 1 } // Isso funciona de forma reativa

</script>

<template>
  <!-- No template não é necessário utilizar .value -->
  <p>{{ count }}</p>
  <button @click="count++">Adicionar +1</button>

</template>
|
<!--
  Ter que usar .value em ref() é uma desvantagem imposta pelas restrições de linguagem do JavaScript.
  No entanto, com as transformações em tempo de compilação,
  podemos melhorar a ergonomia anexando automaticamente .value nos locais apropriados.

  O Vue fornece uma transformação em tempo de compilação que nos permite
  reescrever o componente "ReactiveVariables.vue" de forma abreviada,
  como no código acima.
-->