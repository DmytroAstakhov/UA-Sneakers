<script setup>
import DrawerHead from '@/components/DrawerHead.vue'
import CartItemList from '@/components/CartItemList.vue'
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
    <drawer-head />

    <cart-item-list />

    <div class="flex flex-col gap-4 my-7">
      <div class="flex gap-2 items-center">
        <span>Разом:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <span class="font-bold">21498 UAH</span>
      </div>

      <div class="flex gap-2 items-center">
        <span>Налог 5%:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <span class="font-bold">1050 UAH</span>
      </div>

      <button
        disabled=""
        class="transition cursor-pointer bg-lime-500 w-full rounded-xl py-3 text-white disabled:bg-slate-300 hover:bg-lime-600 active:bg-lime-700"
      >
        Оформити замовлення
      </button>
    </div>
  </div>
</template>
