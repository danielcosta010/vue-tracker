<template>
  <section>
    <strong class="cronometro">
      {{ tempoDecorrido }}
    </strong>
  </section>
</template>

<script lang="ts">
  import { defineComponent } from 'vue'

  export default defineComponent ({
    name: 'CronometroTempo',
    props: {
      contador: {
        type: Number,
        default: 0
      }
    },
    computed: {
      tempoDecorrido () : string {
        return new Date(this.contador * 1000).toISOString().substr(11, 8)
      }
    }
  })

</script>

<style>
.cronometro {
  color: var(--texto-primario);
}
</style>