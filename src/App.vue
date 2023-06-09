<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <OFormulario />
      <div class="lista">
        <ATarefa />
      </div>
    </div>
  </main>
</template>

<script>
import BarraLateral from './components/BarraLateral.vue'
import OFormulario from './components/OFormulario.vue'
import ATarefa from './components/ATarefa.vue'

export default {
  name: "App",
  components: { BarraLateral, OFormulario, ATarefa }
}
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
