<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="product in products">
        <!-- <NuxtLink :to="`/products/${product.id}`"> {{ product.title }} </NuxtLink> -->
        <ProductCard :product="product" />
      </div>
    </div>
  </div>
</template>

<script setup>
// Fetch the products
const { data: products } = await useFetch('https://api.escuelajs.co/api/v1/products')

useHead({
  title: 'Nuxt Dojo | Merch',
  meta: [
    { name: 'description', content: 'Nuxt 3 Merch' }
  ]
})

definePageMeta({
  layout: 'products',
});
</script>

<style lang="scss" scoped></style>