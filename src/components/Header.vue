<script setup>

</script>

<template>
  <header class="flex items-center justify-between border-b-2 border-b-slate-200 py-10 px-5">

    <div class="flex items-center gap-4">
      <img class="w-10 h-10" src="/logo.png" alt="Logo">
      <div>
        <h2 class="font-bold text-xl uppercase">VUE SNEAKERS</h2>
        <p class="text-slate-300 text-s">Магазин лучших кроссовок</p>
      </div>
    </div>

    <ul class="flex items-center gap-10">
      <li class="flex items-center gap-3">
        <img src="/cart.svg" alt="cart">
        <b class="text-gray-400 hover:text-black transition-colors cursor-pointer">1205 руб</b>
      </li>
      <li class="flex items-center gap-3">
        <img src="/heart.svg" alt="cart">
        <span class="text-gray-400 hover:text-black transition-colors cursor-pointer">Закладки</span>
      </li>
      <li class="flex items-center gap-3">
        <img src="/profile.svg" alt="cart">
        <span class="text-gray-400 hover:text-black transition-colors cursor-pointer">Профиль</span>
      </li>
    </ul>
  </header>
</template>

<style scoped>

</style>