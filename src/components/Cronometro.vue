<template>
  <section>
    <strong>
      {{ tempoDecorrido }}
    </strong>
  </section>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

export default defineComponent({
    name:'CronometroMenu',
    props: {
        tempoSegundos:{
            type: Number,
            default: 0
        }
    },
    computed:{ //Monitora uma informação e conforme essa informação é alterada ele computa e reage a ela
    tempoDecorrido() : string{
      return new Date(this.tempoSegundos * 1000).toISOString().substr(11,8)
    }
  },
})


</script>


