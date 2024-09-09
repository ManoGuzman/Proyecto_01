<script>
  export default {
    async asyncData({ $content }) {
      const books = await $content('arquitectos').fetch()
      return {
        books
      }
    }
  }
</script>

<template>
  <div class="container">
   <HeaderView />
   <h3 style="margin-top: 15px">Información de Arquitectos</h3>
    <p>Esta sección presenta la información sobre los arquitectos</p>
   <ul>
     <li v-for="book in books" :key="book.slug">
       <NuxtLink :to="{ name: 'books-slug', params: { slug: book.slug } }">{{book.name}}</NuxtLink>
     </li>
   </ul>
   <FooterView />
 </div>
</template>