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
	   by {{edificio.author}}</br>
	   User Rating: {{edificio.userRating}}; Year: {{edificio.year}};</br>
	   Price: {{edificio.price}}; Genere: {{edificio.genre}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>