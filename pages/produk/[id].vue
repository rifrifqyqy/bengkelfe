<template>
  <NuxtPage :datatrait="desdata" />
</template>

<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();

const id = Number(route.params.id);
const apiUrl = "http://localhost:8080/bengkelbe/dataproduk";
const { data, error } = await useFetch(apiUrl);

if (error.value) {
  console.error("Error fetching data:", error.value);
}
const desdata = data.value.find((destination) => destination.id === id);



useHead({
  title: `MONRO | ${desdata.produk_name}`,
  meta: [{ name: "description", content: "Produk Spareparts" }],
});
</script>

<style scoped></style>
