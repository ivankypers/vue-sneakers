<script setup>

import DrawerHead from "./DrawerHead.vue";
import CartItem from "./CartItem.vue";
import CartListItem from "./CartListItem.vue";
</script>

<template>

  <div class="fixed top-0 left-0 w-full h-full bg-black z-10 opacity-70"></div>
  <div class="flex flex-col bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
    <DrawerHead />

    <CartListItem />

    <div class="flex flex-col gap-5">

      <div class="flex gap-3">
        <span>Итого:</span>
        <div class="border-b border-dashed flex-1"></div>
        <b>21 498 руб.</b>
      </div>

      <div class="flex gap-3">
        <span>Налог 5%: </span>
        <div class="border-b border-dashed flex-1"></div>
        <b>1074 руб.</b>
      </div>

      <button class="w-full bg-lime-500 rounded-xl py-3 text-white cursor-pointer hover:bg-lime-700 transition-colors active:bg-lime-900 disabled:bg-slate-300">
        Оформить заказ
      </button>

    </div>

  </div>

</template>

