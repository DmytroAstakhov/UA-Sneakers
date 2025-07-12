<script setup>
import ProductCard from './ProductCard.vue'

defineProps({
  items: Array,
})

const emit = defineEmits(['addToFavorite'])
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <product-card
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :imageUrl="item.imageUrl"
      :price="item.price"
      :on-click-favorite="() => emit('addToFavorite', item)"
      :is-favorite="item.isFavorite"
    />
  </div>
</template>
