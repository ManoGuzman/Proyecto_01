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
     </div>
     <div class="six columns">
       <h4>{{ciudad.name}}</h4>
       Poblacion: {{ciudad.poblacion}}</br>
       Clima: {{ciudad.clima}}</br>
       Economia: {{ciudad.economia}}</br>
       Infraestructura: {{ciudad.infraestructura}}</br> 
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>