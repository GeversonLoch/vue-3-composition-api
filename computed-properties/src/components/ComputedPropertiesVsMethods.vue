<script setup>
import { computed, reactive } from 'vue'

const otherData = reactive({
  count: 0
})

const time = computed(() => {
  const date = new Date();
  return `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`
})

function getTime() {
  const date = new Date();
  return `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`
}
</script>

<template>
  <p>{{ time }}</p>
  <p>{{ getTime() }}</p>
  <p>{{ otherData.count }} N° Atualizações do Template:</p>
  <button @click="otherData.count++">Incrementar +1</button>
  <p>
    Note que utilizando a função(getTime) o template é atualizado a cada alteração de outras propriedades(dependências) reativas,<br>
    isso tornara o template inchados e difíceis de manter em uma escala maior.
  </p>
</template>

<!--
  A diferença de utilizar as 'Computed Properties' ao inves de funções normais é que 
  as propriedades computadas são armazenadas em cache com base em suas 'dependências reativas'.

  Ou seja, uma propriedade computada só será atualizará quando algumas de suas 'dependências reativas' forem alteradas.
-->

<!--
  Por que precisamos de cache?

  Imagine que temos uma propriedade computada cara, uma lista de itens por exemplo,
  que requer fazer um loop através de uma enorme matriz e fazer muitos cálculos.
  Então podemos ter outras propriedades computadas que, por sua vez, dependem de list.

  Sem cache, estaríamos executando uma lista getter's muito mais vezes do que o necessário!
  Nos casos em que você não deseja armazenar em cache, use uma chamada de método.
-->