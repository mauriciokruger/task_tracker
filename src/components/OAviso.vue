<template>
  <div class="box has-text-weight-bold" :style="estilos">
    <slot></slot>
  </div>
</template>

<script>
import { defineComponent } from "vue"
export default defineComponent({
  name: 'OAviso',
  data () {
    return {
      estilos: {
        background: '#FAF0CA'
      }
    }
  }
});
</script>