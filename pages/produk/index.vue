<template>
  <section class="flex flex-col gap-8">
    <div class="ml-2 flex flex-col items-center self-center">
      <h1 class="text-[42px] font-semibold text-yellow-500">Semua Produk</h1>
      <p class="text-dark-200">
        Berbagai produk dan layanan di MONRO autoservices
      </p>
    </div>
    <p v-if="pending">
      <div
        class="grid justify-items-center gap-y-8 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4"
      >
        <CardTravel
          v-for="(item, index) in prods"
          :key="index"
          :image="`https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTWN8hLKJungcUipWLReON9fse4yZcyB0rzNw&s`"
          :title="`Loading...`"
          :desc="`Loading...`"
          :rating="`Loading...`"
          :price="`Loading...`"
          :maps="`Loading...`"
          :to="`Loading...`"
        />
      </div>
    </p>
    <template v-else class="">
      <div
        class="grid justify-items-center gap-y-8 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4"
      >
        <CardTravel
          v-for="(item, index) in prods"
          :key="index"
          :image="`https://porto-management-rifqy.vercel.app/${item.imageUrl}`"
          :title="item.title"
          :desc="item.description"
          :rating="4.8"
          :price="formatRupiah(item.price)"
          :maps="item.maps"
          :to="`/produk/${item.id}`"
        />
      </div>
    </template>
  </section>
</template>

<script setup>
const apiUrl = "https://porto-management-rifqy.vercel.app/api/porto";
const {
  pending,
  data: prods,
  error,
} = await useFetch(apiUrl, {
  lazy: true,
  retry: true,
});

useHead({
  title: "MONRO | Daftar Produk",
  meta: [{ name: "description", content: "Daftar Produk" }],
});
</script>

<style scoped></style>
