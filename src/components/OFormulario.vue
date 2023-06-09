<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="descricao"
        >
      </div>
      <div class="column">
        <OTemporizador @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import OTemporizador from './OTemporizador.vue'
export default defineComponent ({
  name: 'OFormulario',
  components:  { OTemporizador },
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido) {
      console.log(tempoDecorrido)
      this.descricao = ''
    }
  }
})
</script>