<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <OFormulario @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <ATarefa :tarefa="tarefa" v-for="(tarefa, index) in tarefas" :key="index" />
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
  components: { 
    BarraLateral,
    OFormulario,
    ATarefa
  },
  data () {
    return {
      tarefas: []
    }
  },
  methods: {
    salvarTarefa (tarefa) {
      this.tarefas.push(tarefa)
    }
  }
}
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
