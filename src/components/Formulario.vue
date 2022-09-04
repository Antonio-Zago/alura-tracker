<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para a criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa deseja iniciar?"
        />
      </div>
      <div class="column">
        <TemporizadorMenu/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorMenu from "./Temporizador.vue";

export default defineComponent({
  components: { TemporizadorMenu },
  name: "FormularioTarefa",
});
</script>

<style scoped>
</style>
