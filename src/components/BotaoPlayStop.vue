<template>
  <button class="button" @click="clicado" :disabled="desabilitado">
    <span class="icon">
      <i :class="icone"></i>
    </span>
    <span>{{ texto }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BotaoPlayStop',
  emits: ['clicado'],
  props: {
    texto: {
      type: String,
      required: true
    },
    icone: {
      type: String,
      required: true
    },
    desabilitado: Boolean,
  },
  methods: {
    clicado() : void{
      this.$emit('clicado');
    }
  }
})

</script>