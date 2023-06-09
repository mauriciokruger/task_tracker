<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        Descrição da tarefa
      </div>
      <div class="column ">
        <OCronometro :tempoEmSegundos="15" />
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import OCronometro from './OCronometro.vue'
export default defineComponent ({
  name: 'ATarefa',
  components:  { OCronometro },
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
