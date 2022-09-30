<script setup> // Veja como é mais simples se adicionarmos 'setup' a tag script de um SFC!
import { reactive } from 'vue'
/*
export default {

  setup() {*/

    const state = reactive({ count: 0 })
    
    function increment() {
      state.count++
    }
  /*
    return {
      state,
      increment
    }
  }

}*/

</script>
  
<template>
  <p>state.count {{ state.count }}</p>

  <button @click="increment">Adicionar +1</button>
</template>
  
<!--
  A exposição manual de estado e métodos setup() pode ser detalhada.
  Felizmente, só é necessário quando não estiver usando uma etapa de compilação.
  Ao usar componentes de arquivo único (SFCs), podemos simplificar bastante o uso com <script setup>:

  No código acima podemos observar a abreviação do mesmo código do componente ReactiveState.vue
-->