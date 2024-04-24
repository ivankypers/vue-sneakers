<script setup>
  const props = defineProps({
    imageUrl: String,
    title: String,
    price: Number,
    isFavorite: Boolean,
    isAdded: Boolean,

    onClickAdd: Function,
    onClickFavorite: Function,

  })
</script>

<template>
  <div class="flex flex-col gap-3 relative bg-white rounded-3xl border-2 border-slate-100 hover:-translate-y-2 hover:shadow-lg transition p-8">

    <img @click="onClickFavorite" :src="!isFavorite ? '/like-1.svg': '/like-2.svg'" alt="Like1" class="absolute top-8 left-8 cursor-pointer">
    <img :src="imageUrl" alt="Sneakers" class="w-60 h-52">
    <p class="max-w-56">{{ title }}</p>
    <div class="flex items-center justify-between">
      <div class="flex flex-col">
        <span class="text-slate-300">Цена:</span>
        <b>{{ price }} руб.</b>
      </div>
      <button @click="onClickAdd">
        <img :src="!isAdded ? '/plus.svg': '/checked.svg'" alt="">
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>