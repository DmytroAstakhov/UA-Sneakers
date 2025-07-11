<script setup>
import { onMounted, reactive, ref, watch } from 'vue'
import axios from 'axios'

import HeaderMenu from '@/components/HeaderMenu.vue'
import CardList from '@/components/CardList.vue'
// import SideDrawer from '@/components/SideDrawer.vue'

const items = ref([])

const filters = reactive({
  sortBy: 'title',
  searchQuery: '',
})

const onChangeSelect = (event) => {
  filters.sortBy = event.target.value
}

const onChangeSearchInput = (event) => {
  filters.searchQuery = event.target.value
}

const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy,
    }

    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    const { data } = await axios.get(`https://015b6f158224e20f.mokky.dev/items`, {
      params,
    })
    items.value = data
  } catch (error) {
    console.log(error)
  }
}

onMounted(fetchItems)
watch(filters, fetchItems)
</script>

<template>
  <!--  <side-drawer />-->
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-xl mt-10">
    <header-menu />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Всі кросівки</h2>

        <div class="flex gap-4">
          <select
            @change="onChangeSelect"
            class="py-2 px-3 border border-gray-300 rounded-md outline-none"
          >
            <option value="name">По назві</option>
            <option value="price">По ціні ⬆️</option>
            <option value="-price">По ціні ⬇️</option>
          </select>

          <div class="relative">
            <img class="absolute left-3 top-3" src="/search.svg" alt="" />
            <input
              @input="onChangeSearchInput"
              class="border border-gray-300 rounded-md py-2 pl-11 pr-4 outline-none focus:border-gray-500"
              type="text"
              placeholder="Пошук..."
            />
          </div>
        </div>
      </div>

      <div class="mt-10">
        <card-list :items="items" />
      </div>
    </div>
  </div>
</template>
