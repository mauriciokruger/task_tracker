<template>
  <section>
    <!--  Repare que eu não vou executar uma função, eu só estou chamando o tempo decorrido, porque o Vue sabe que por baixo dos panos o 'tempoDecorrido' vai funcionar como se fosse uma propriedade do estado do componente, só que calculado. Então nós o definimos como método, porém acessamos como uma propriedade. -->
    <strong class="display">{{ tempoDecorrido }}</strong>
  </section>
</template>

<script>
  import { defineComponent } from 'vue'
  export default defineComponent ({
    name: 'OCronometro',
    props: {
      tempoEmSegundos: {
        type: Number,
        default: 0
      }
    },
    computed: {
      // vai monitorar uma informação, e conforme essa informação for alterada ele vai reagir e vai se atualizar.
      tempoDecorrido () {
        return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
      }
    },
  })
</script>
<style scoped>
.display {
  color: var(--texto-primario);
}
</style>