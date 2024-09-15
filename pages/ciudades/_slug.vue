<script>
  export default {
    async asyncData({ $content, params }) {
      const ciudad = await $content('ciudades', params.slug).fetch()
      return { ciudad }
    }
  }
</script>

<template>
  <div class="container">
   <HeaderView />
   <div class="row">
    <div class="three columns">
        <img class="u-max-full-width" :src="'/images/'+ciudad.image">
     </div>
     <div class="six columns">
       <h4>{{ciudad.name}}</h4>
       <b>Poblacion:</b> {{ciudad.poblacion}}</br>
       <b>Clima:</b> {{ciudad.clima}}</br>
       <b>Economia:</b> {{ciudad.economia}}</br>
       <b>Infraestructura:</b> {{ciudad.infraestructura}}</br>
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>