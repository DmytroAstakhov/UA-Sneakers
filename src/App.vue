<script setup>
import HeaderMenu from '@/components/HeaderMenu.vue'
import CardList from '@/components/CardList.vue'
import SideDrawer from '@/components/SideDrawer.vue'
</script>

<template>
  <!--  <side-drawer />-->
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-xl mt-10">
    <header-menu />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Всі кросівки</h2>

        <div class="flex gap-4">
          <select class="py-2 px-3 border border-gray-300 rounded-md outline-none">
            <option>По назві</option>
            <option>По ціні ⬆️</option>
            <option>По ціні ⬇️</option>
          </select>

          <div class="relative">
            <img class="absolute left-3 top-3" src="/search.svg" alt="" />
            <input
              class="border border-gray-300 rounded-md py-2 pl-11 pr-4 outline-none focus:border-gray-500"
              type="text"
              placeholder="Пошук..."
            />
          </div>
        </div>
      </div>

      <card-list />
    </div>
  </div>
</template>
