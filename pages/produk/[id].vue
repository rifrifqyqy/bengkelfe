<template>
  <NuxtPage :datatrait="desdata" />
</template>

<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();

const id = Number(route.params.id);
const apiUrl = "https://8744-110-138-93-77.ngrok-free.app/bengkelbe/dataproduk";
const { data, error } = await useFetch(apiUrl);

if (error.value) {
  console.error("Error fetching data:", error.value);
}
const desdata = data.value.find((destination) => destination.id === id);



useHead({
  title: `TouTour | ${desdata.produk_name}`,
  meta: [{ name: "description", content: "Destinasi Wisata" }],
});
</script>

<style scoped></style>
