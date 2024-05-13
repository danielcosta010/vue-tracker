<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <CronometroTempo :contador="contador" />
    <button class="button" @click="iniciar" :disabled="cronometroRodando">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="pausar" :disabled="!cronometroRodando">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CronometroTempo from './CronometroTempo.vue'

export default defineComponent({
  name: 'TemporizadorTempo',
  data() {
    return {
      contador: 0,
      stopContador: 0,
      cronometroRodando: false
    }
  },
  components: {
    CronometroTempo
  },
  methods: {
    iniciar() {
      this.cronometroRodando = true
      this.stopContador = setInterval(() => {
        this.contador += 1
      }, 1000)
    },
    pausar() {
      this.cronometroRodando = false
      clearInterval(this.stopContador);      
    }
  }

})
</script>