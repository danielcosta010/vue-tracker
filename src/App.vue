<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormCount @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaConcluida v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        
      </div>
    </div>
  </main>
  
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormCount from './components/FormCount.vue';
import TarefaConcluida from './components/TarefaConcluida.vue';
import ITarefa from './interfaces/ITarefa';



export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormCount,
    TarefaConcluida
  },
  data() {
    return {
      tarefas: [] as ITarefa[]
    }
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    }
  }
});
</script>

<style >
.lista {
  padding: 1.25rem;
}
</style>
