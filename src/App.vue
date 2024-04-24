<script setup>
import {onMounted, ref, reactive, watch} from "vue";

import Header from "./components/Header.vue";
import CardList from "./components/CardList.vue";
import Drawer from "./components/Drawer.vue";
import axios from "axios";

const items = ref([])

const filters = reactive({
  sortBy: 'title',
  searchQuery: ''
})

const fetchItems = async () => {
  const params = {
    sortBy: filters.sortBy
  }
  if (filters.searchQuery) {
    params.title = `*${filters.searchQuery}*`
  }
  try {
    const { data } = await axios.get('https://82f30c081443cd59.mokky.dev/sneakers', {
      params
    })

    items.value = data
  } catch(err) {
    console.log(err)
  }
}

const onChangeSelect = function (event) {
  filters.sortBy = event.target.value;

}

const onChangeInput = function (event) {
  filters.searchQuery = event.target.value;
}

onMounted(fetchItems)
watch(filters, fetchItems)

</script>

<template>

  
  <div class="bg-white w-4/5 h-max rounded-xl shadow-xl mx-auto p-10 mt-10">
    <Header />


    <div class="py-10">

      <div class="flex items-center justify-between mb-10">
        <h2 class="text-xl font-bold">Все кроссовки</h2>

        <div class="flex items-center gap-4">
          <select @change="onChangeSelect" class="border-2 rounded-md py-2 px-4 outline-none">
            <option value="name">По названию</option>
            <option value="price">Дешевые</option>
            <option value="-price">Дорогие</option>
          </select>

          <div class="relative">
            <img class="absolute top-4 left-4" src="/search.svg" alt="">
            <input @input="onChangeInput" class="border-2 rounded-md py-2 pl-10 pr-4 outline-none focus:border-gray-400" placeholder="Поиск">
          </div>
        </div>
        
      </div>


      <CardList :items="items" />
    </div>

  </div>
</template>

<style scoped lang="scss">

</style>


