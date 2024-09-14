<script>
  export default {
    async asyncData({ $content, params }) {
      const arquitecto = await $content('arquitectos', params.slug).fetch()
      return { arquitecto }
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
       <h4>{{arquitecto.name}}</h4>
      Nacionalidad: {{arquitecto.nacionalidad}}</br>
      Estilo: {{arquitecto.estilo}}</br>
      Obras Notables: {{arquitecto.obras_notables}}</br>
      Distincion: {{arquitecto.distincion}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>