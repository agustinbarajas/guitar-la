<script setup lang="ts">
import { Guitar } from "../types";

const { guitar } = defineProps<{ guitar: Guitar }>();
</script>

<template>
  <article class="my-4 flex items-center">
    <div class="w-1/3 h-full">
      <img
        :src="'/img/' + guitar.image + '.jpg'"
        :alt="guitar.name"
        class="object-cover p-1 h-full"
      />
    </div>
    <div class="flex flex-col justify-center w-2/3 h-full">
      <h3 class="text-black text-xl font-bold uppercase">
        {{ guitar.name }}
      </h3>
      <p>{{ guitar.description }}</p>
      <p class="font-black text-current text-2xl">${{ guitar.price }}</p>
      <button
        class="border px-4 py-2 rounded-md bg-black text-white hover:bg-white hover:text-black w-full"
      >
        Add to cart
      </button>
    </div>
  </article>
</template>
