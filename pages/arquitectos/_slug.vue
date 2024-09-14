<script>
  export default {
    async asyncData({ $content, params }) {
      const arquitecto = await $content('edificios', params.slug).fetch()
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
	   by {{arquitecto.author}}</br>
	   User Rating: {{arquitecto.userRating}}; Year: {{arquitecto.year}};</br>
	   Price: {{arquitecto.price}}; Genere: {{arquitecto.genre}}
	 </div>
	 <div class="two columns"></div>
   </div>
   <FooterView />
 </div>
</template>