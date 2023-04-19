<template>
  <div>
    <h2>Sistema de Gestión</h2>
    <li v-for="ges in gestiones" :key="ges.id"> <!--lista todas las gestiones disponibles -->
      {{ ges.id }} {{ ges.desc }}
    </li>
    <button v-on:click="OrdenarPorId">OrdenarPorId</button> <!--lista todas las gestiones disponibles -->
    <Detalle @agregarDetalle="agregarGestion"/>
  </div>
</template>

<script>
import Detalle from './Detalle.vue'
export default {
  components: { Detalle},
  data() {
    return {
      gestiones: [{id:10,desc:"Envio mail"},{id:11,desc:"Envio whatsapp"}],
    }
  },
  methods: {
    agregarGestion(gestion) {
      this.gestiones.push(gestion);      
    },
    OrdenarPorId(){
      this.gestiones.sort((a,b)=>a.id.localeCompare(b.id))
    }
  }
}
</script>



<style>

</style>