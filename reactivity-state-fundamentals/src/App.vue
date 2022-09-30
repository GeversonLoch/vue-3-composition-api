<script>
import ReactiveState from './components/ReactiveState.vue'
import ScriptSetup from './components/ScriptSetup.vue'
import ReactiveProxy from './components/ReactiveProxy.vue'
import ReactiveVariables from './components/ReactiveVariables.vue'
import NextTick from './components/NextTick.vue'

export default {
  components: {
    ReactiveState,
    ScriptSetup,
    ReactiveProxy,
    ReactiveVariables,
    NextTick
  }
}
</script>

<template>
  <h1>Reactivity State Fundamentals</h1>

  <ReactiveState />
  <hr>
  <ScriptSetup />
  <hr>
  <ReactiveProxy/>
  <hr>
  <NextTick/>
  <hr>
  <ReactiveVariables/>
</template>

<style>
  /* Basic CSS for the page, ignore this! */
  h1 { color: #42B883; }
  h2,h3,h4 { color: #424242; }
  p { color:#616161; }
</style>