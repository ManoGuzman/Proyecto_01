<script>
  export default {
    async asyncData({ $content, params }) {
      const edificio = await $content('edificios', params.slug).fetch()
      return { edificio }
    }
  }
</script>

<template>
  <div class="container">
   <HeaderView />
   <div class="row">
     <div class="three columns">
     </div>
     <div class="six columns">
       <h4>{{edificio.name}}</h4>
	   Arquitecto: {{edificio.arquitecto}}</br>
     Altura: {{edificio.altura}}</br>
	   Ubicacion: {{edificio.ubicacion}}</br>
     Annio Finalizacion: {{edificio.annnio_final}}</br>
	   Capacidad: {{edificio.capacidad}}</br> 
     usos: {{edificio.uso}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>