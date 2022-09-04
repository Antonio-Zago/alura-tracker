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
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong>
              {{tempoDecorrido}}
            </strong>
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

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FormularioTarefa",
  data(){ //Define o estado inicial do componente
    return{
      tempoSegundos:0,
      cronometro:0
    }
  },
  computed:{ //Monitora uma informação e conforme essa informação é alterada ele computa e reage a ela
    tempoDecorrido() : string{
      return new Date(this.tempoSegundos * 1000).toISOString().substr(11,8)
    }
  },
  methods:{
    iniciar(){
      //Começar a contagem
      this.cronometro = setInterval(() => { //Método do JS
        this.tempoSegundos += 1;
      }, 1000)
    },
    finalizar(){
      clearInterval(this.cronometro)
    }
  }
});
</script>

<style scoped>
</style>
