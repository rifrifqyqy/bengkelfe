<template>
  <NuxtPage :datatrait="desdata" />
</template>

<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();

const id = Number(route.params.id);
const apiUrl = "https://porto-management-rifqy.vercel.app/api/porto";
const { data, error } = await useFetch(apiUrl);

if (error.value) {
  console.error("Error fetching data:", error.value);
}
const desdata = data.value.find((item) => item.id === id);



useHead({
  title: `MONRO | ${desdata.produk_name}`,
  meta: [{ name: "description", content: "Produk Spareparts" }],
});
</script>

<style scoped></style>
