<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <OFormulario @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <ATarefa :tarefa="tarefa" v-for="(tarefa, index) in tarefas" :key="index" />
        <OAviso v-if="listaEstaVazia">
          Você não está muito produtivo hoje :(
        </OAviso>
      </div>
    </div>
  </main>
</template>

<script>
import BarraLateral from './components/BarraLateral.vue'
import OFormulario from './components/OFormulario.vue'
import ATarefa from './components/ATarefa.vue'
import OAviso from './components/OAviso.vue'

export default {
  name: "App",
  components: { 
    BarraLateral,
    OFormulario,
    ATarefa,
    OAviso
  },
  data () {
    return {
      tarefas: []
    }
  },
  computed: {
    listaEstaVazia () {
      return this.tarefas.length === 0
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
