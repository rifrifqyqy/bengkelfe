<template>
    <div class="card">
      <section class="flex flex-col gap-2">
        <img :src="image" alt="" class="image" />
        <div class="mt-1 flex justify-between gap-4">
          <div
            class="flex items-center gap-2 rounded-sm bg-zinc-200 px-2 h-6 w-40 font-semibold text-zinc-500"
          >
            <p>{{ rating }}</p>
          </div>
          <NuxtLink :to="maps">
            <div
              class=" items-center gap-2 rounded-full bg-amber-100 px-2 font-semibold text-mainn-50 hidden"
            >
              <img src="/images/map.svg" class="w-[20px]" alt="" />
              <p>{{ location }}</p>
            </div>
          </NuxtLink>
        </div>
        <article class="header" :class="{ 'pb-2': !showPrice }">
          <div class="body">
            <h1 class="bg-zinc-200 h-6 w-56 rounded-sm">{{ props.title }}</h1>
            <p>{{ desc }}</p>
          </div>
        </article>
        <div v-if="showPrice" class="price">
          <h1>{{ price }}</h1>
        </div>
      </section>
  
      <div v-if="showButton" class="footer">
        <NuxtLink class="w-full">
          <ButtonPrimary styled="bg-zinc-200 h-10 rounded-md">
            
          </ButtonPrimary>
        </NuxtLink>
      </div>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    image: String,
    title: String,
    rating: Number,
    location: String,
    price: String,
    to: Object,
    desc: String,
    maps: String,
    showButton: {
      type: Boolean,
      default: true,
    },
    showPrice: {
      type: Boolean,
      default: true,
    },
  });
  </script>
  
  <style scoped>
  .card {
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
    @apply flex w-fit flex-col justify-between rounded-md bg-white p-2 text-dark-50;
  
    .image {
      @apply h-[260px] w-[260px] rounded-md object-cover;
    }
    
    .price {
      @apply border-t pt-2 h-7 rounded-sm w-24 bg-zinc-200 text-xl font-bold text-yellow-500;
    }
    .body {
      @apply min-w-fit max-w-min;
      p {
        @apply line-clamp-2 text-dark-200;
      }
    }
    .footer {
      @apply mt-4 flex w-full justify-between gap-2;
    }
  }
  </style>
  