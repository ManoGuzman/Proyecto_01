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
        <img class="u-max-full-width" :src="'/images/'+arquitecto.image">
     </div>
     <div class="six columns">
       <h4>{{arquitecto.name}}</h4>
      <b>Nacionalidad:</b> {{arquitecto.nacionalidad}}</br>
      <b>Estilo:</b> {{arquitecto.estilo}}</br>
      <b>Obras Notables:</b> {{arquitecto.obras_notables}}</br>
      <b>Distincion:</b> {{arquitecto.distincion}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>