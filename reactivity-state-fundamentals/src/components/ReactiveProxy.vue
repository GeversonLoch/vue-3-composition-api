<script setup>
import { reactive } from 'vue'

const raw = {}
const proxy = reactive(raw)

</script>

<template>
  <p>Proxy NÃO é igual à variável original: {{ raw === proxy }}</p>
</template>