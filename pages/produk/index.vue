<template>
  <section class="flex flex-col gap-8">
    <div class="ml-2 flex flex-col items-center self-center">
      <h1 class="text-[42px] font-semibold text-yellow-500">Semua Produk</h1>
      <p class="text-dark-200">
        Berbagai produk dan layanan di MONRO autoservices
      </p>
    </div>
    <p v-if="pending">Loading...</p>
    <template v-else class="">
      <div
        class="grid justify-items-center gap-y-8 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4"
      >
        <CardTravel
          v-for="(item, index) in data"
          :key="index"
          :image="`https://8744-110-138-93-77.ngrok-free.app/bengkelbe/${item.image.file_path}`"
          :title="item.produk_name"
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
const apiUrl = "https://8744-110-138-93-77.ngrok-free.app/bengkelbe/dataproduk";
const { pending, data, error } = await useFetch(apiUrl, {
  lazy: false,
  headers: {
    "Access-Control-Allow-Origin": "*",
  },
});
useHead({
  title: "TouTour | Destinasi",
  meta: [{ name: "description", content: "Destinasi Wisata" }],
});
</script>

<style scoped></style>
