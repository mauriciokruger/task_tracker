<template>
  <section class="is-flex is-align-items-center is-justify-content-space-between">
    <OCronometro :tempoEmSegundos="tempoEmSegundos" />
    <OsBotoes @clicado="iniciar" icone="fas fa-play" texto="play" :desabilitado="cronometroRodando" />
    <OsBotoes @clicado="finalizar" icone="fas fa-stop" texto="stop" :desabilitado="!cronometroRodando" />
  </section>
</template>

<script>
import { defineComponent } from 'vue'
import OCronometro from './OCronometro.vue'
import OsBotoes from './OsBotoes.vue'
export default defineComponent ({
  name: 'OTemporizador',
  components:  { OCronometro, OsBotoes },
  emits: ['aoTemporizadorFinalizado'],
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false
    }
  },
  methods: {
    iniciar () {
      this.cronometroRodando = true
      this.cronometro = setInterval (() => {
        this.tempoEmSegundos += 1
      }, 1000)
    },
    finalizar () {
      this.cronometroRodando = false
      clearInterval(this.cronometro)
      this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
      this.tempoEmSegundos = 0
    }
  }
})
</script>