<script setup>
import { ref } from 'vue';

defineProps({
  title: String,
  img: String,
  price: Number,
});

const isLiked = ref(false);

const onClick = () => {
  isLiked.value = !isLiked.value;
};
</script>

<template>
  <div
    class="relative flex flex-col w-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-xl hover:transform hover:-translate-y-2"
  >
    <div @click="onClick" class="absolute top-8 left-8">
      <img :src="isLiked ? '/like-1.svg' : '/like-2.svg'" alt="Favorite" />
    </div>
    <img :src="img" class="w-full" alt="Sneaker" />
    <p>{{ title }}</p>
    <div class="flex justify-between mt-5">
      <div class="flex flex-col gap-2">
        <span class="text-slate-200">Цена:</span>
        <span class="font-bold">{{ price }} руб.</span>
      </div>
      <img src="/plus.svg" alt="Plus" />
    </div>
  </div>
</template>
