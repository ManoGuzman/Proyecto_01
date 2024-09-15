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
        <img class="u-max-full-width" :src="'/images/'+edificio.image">
     </div>
     <div class="six columns">
       <h4>{{edificio.name}}</h4>
       <b>Arquitecto:</b> {{edificio.arquitecto}}</br>
       <b>Altura:</b> {{edificio.altura}}</br>
       <b>Ubicacion:</b> {{edificio.ubicacion}}</br>
       <b>Annio Finalizacion:</b> {{edificio.annnio_final}}</br>
       <b>Capacidad:</b> {{edificio.capacidad}}</br> 
       <b>Usos:</b> {{edificio.uso}}</br>
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>