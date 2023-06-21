<template>
  <OAviso>
    <div class="columns">
      <div class="column is-7">
        {{tarefa.descricao || 'Tarefa sem descrição'}}
      </div>
      <div class="column">
        <OCronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </OAviso>
</template>

<script>
import { defineComponent } from 'vue'
import OCronometro from './OCronometro.vue'
import OAviso from './OAviso.vue'
export default defineComponent ({
  name: 'ATarefa',
  props: ['tarefa'],
  components:  { OCronometro, OAviso },
  data () {
    return {
    }
  },
  methods: {}
})
</script>

<style scoped>
.box {background: #FAF0CA;}
</style>
