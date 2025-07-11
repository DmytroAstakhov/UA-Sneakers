<script setup>
import ProductCard from './ProductCard.vue'
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <product-card
      imageUrl="public/sneakers/sneakers-1.jpg"
      title="Мужские Кроссовки Nike Blazer Mid Suede"
      :price="5000"
      :isAdded="false"
      :isFavorite="false"
    />
  </div>
</template>
