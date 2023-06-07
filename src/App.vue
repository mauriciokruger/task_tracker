<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <OFormulario />
    </div>
  </main>
</template>

<script>
import BarraLateral from './components/BarraLateral.vue'
import OFormulario from './components/OFormulario.vue'


export default {
  name: "App",
  components: { BarraLateral, OFormulario }
}
</script>

<style>

</style>
