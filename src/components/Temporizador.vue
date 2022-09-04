<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <CronometroMenu :tempoSegundos="tempoSegundos" />
    <button class="button" @click="iniciar" :disabled="cronometroRodando">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="finalizar" :disabled="!cronometroRodando"> 
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CronometroMenu from "./Cronometro.vue";

export default defineComponent({
  components: { CronometroMenu },
  name: "TemporizadorMenu",
  data(){ //Define o estado inicial do componente
    return{
      tempoSegundos:0,
      cronometro:0,
      cronometroRodando: false
    }
  },
  methods:{
    iniciar(){
      //Começar a contagem
      this.cronometroRodando = true;
      this.cronometro = setInterval(() => { //Método do JS
        this.tempoSegundos += 1;
      }, 1000)
    },
    finalizar(){
        this.cronometroRodando = false;
      clearInterval(this.cronometro)
    }
  }
});
</script>