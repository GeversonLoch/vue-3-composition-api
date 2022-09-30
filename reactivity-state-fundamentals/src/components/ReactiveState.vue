<script>
import { reactive } from 'vue'

export default {

  setup() { // 'setup' é um gancho especial dedicado à API de composição.

    const state = reactive({ count: 0 })

    function increment() { // Podemos declarar funções que alteram o estado reativo no mesmo escopo e expô-lo como um método
      state.count++
    }

    return { // Expor o estado ao template
      state,
      increment // Nunca se esqueça de expor as funções também.
    }
  }

}
</script>

<template>
  <p>state.count {{ state.count }}</p>

  <!-- Os métodos expostos são normalmente usados ​​como ouvintes de evento -->
  <button @click="increment">Adicionar +1</button>
</template>