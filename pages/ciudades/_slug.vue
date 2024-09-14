<script>
  export default {
    async asyncData({ $content, params }) {
      const ciudad = await $content('edificios', params.slug).fetch()
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
	   by {{ciudad.author}}</br>
	   User Rating: {{ciudad.userRating}}; Year: {{ciudad.year}};</br>
	   Price: {{ciudad.price}}; Genere: {{ciudad.genre}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>