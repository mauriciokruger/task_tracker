<template>
  <main class="columns is-gapless is-multiline" :class="{ 'modo-escuro': modoEscuroAtivo }">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="trocarTema" />
    </div>
    <div class="column is-three-quarter conteudo">
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
      tarefas: [],
      modoEscuroAtivo: false
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
    },
    trocarTema (modoEscuroAtivo) {
      this.modoEscuroAtivo = modoEscuroAtivo
    }
  }
}
</script>

<style>
.lista {
  padding: 1.25rem;
}
main {
  --bg-primario: #fff;
  --texto-primario: #000;
}
main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}
.conteudo {
  background-color: var(--bg-primario);
}
</style>
