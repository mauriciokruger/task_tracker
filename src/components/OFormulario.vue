<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?">
      </div>
      <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <section>
            <!--  Repare que eu não vou executar uma função, eu só estou chamando o tempo decorrido, porque o Vue sabe que por baixo dos panos o 'tempoDecorrido' vai funcionar como se fosse uma propriedade do estado do componente, só que calculado. Então nós o definimos como método, porém acessamos como uma propriedade. -->
            <strong>{{ tempoDecorrido }}</strong>
          </section>
          <button class="button" @click="iniciar">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalizar">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent ({
  name: 'OFormulario',
  data () {
    return {
      tempoEmSegundos: 0
    }
  },
  computed: {
    // vai monitorar uma informação, e conforme essa informação for alterada ele vai reagir e vai se atualizar.
    tempoDecorrido () {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
    }
  },
  methods: {
    iniciar () {
      setInterval (() => {
        this.tempoEmSegundos += 1
      }, 1000)
      console.log('Iniciando');
    },
    finalizar () {
      console.log('Finalizando');
    }
  }
})
</script>