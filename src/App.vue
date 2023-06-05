<script setup lang="ts">
import { Ref, onMounted, ref } from "vue";
import GuitarCard from "./components/GuitarCard.vue";
import { guitars as staticGuitars } from "./data";
import { Guitar } from "./types";

const guitars: Ref<Guitar[]> = ref([]);

onMounted(() => {
  guitars.value = staticGuitars;
});
</script>

<template>
  <main class="flex flex-col w-full">
    <h2 class="text-center text-4xl font-bold">Guitar collection</h2>

    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 mt-5"
    >
      <GuitarCard v-for="guitar of guitars" :guitar="guitar"></GuitarCard>
    </div>
  </main>
</template>
