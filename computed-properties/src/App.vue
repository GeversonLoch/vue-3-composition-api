<script setup>
  import ComputedProperties from './components/ComputedProperties.vue'
  import ComputedPropertiesVsMethods from './components/ComputedPropertiesVsMethods.vue'
  import WritableComputed from './components/WritableComputed.vue'
</script>

<template>
  <h1>Computed Properties</h1>

  <ComputedProperties />
  <hr>
  <ComputedPropertiesVsMethods />
  <hr>
  <WritableComputed />
</template>

<style>
  /* Basic CSS for the page, ignore this! */
  h1 { color: #42B883; }
  h2,h3,h4 { color: #424242; }
  p { color:#616161; }
</style>