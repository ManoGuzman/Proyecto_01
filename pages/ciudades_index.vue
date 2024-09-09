<script>
  export default {
    async asyncData({ $content }) {
      const books = await $content('ciudades').fetch()
      return {
        books
      }
    }
  }
</script>

<template>
  <div class="container">
   <HeaderView />
   <h3 style="margin-top: 15px">Información de Ciudades</h3>
   <p>Esta sección presenta la información sobre las ciudades</p>
   <ul>
     <li v-for="book in books" :key="book.slug">
       <NuxtLink :to="{ name: 'books-slug', params: { slug: book.slug } }">{{book.name}}</NuxtLink>
     </li>
   </ul>
   <FooterView />
 </div>
</template>