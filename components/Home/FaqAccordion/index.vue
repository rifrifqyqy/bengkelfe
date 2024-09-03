<template>
  <UAccordion :items="items" :ui="{ wrapper: 'flex flex-col w-full gap-2' }">
    <template #default="{ item, index, open }">
      <UButton
        variant="ghost"
        class="group flex justify-between bg-white shadow-sm transition-all duration-300 hover:bg-mainn-100"
        :ui="{ rounded: 'rounded-none', padding: {} }"
        :class="[open && 'bg-mainn-100']"
      >
        <span
          class="truncate px-4 py-2 text-xl text-mainn-50 group-hover:text-white max-sm:px-2 max-sm:py-0 max-sm:text-[16px]"
          :class="[open && 'text-white']"
        >
          {{ item.label }}</span
        >

        <template #trailing>
          <UIcon
            name="i-heroicons-chevron-down-20-solid"
            class="h-5 w-5 min-w-6 transform text-mainn-50 transition-transform duration-200 group-hover:text-white"
            :class="[open && 'rotate-180 text-white']"
          />
        </template>
      </UButton>
    </template>
    <template #item="{ item }">
      <p
        class="px-4 text-lg text-dark-100 max-sm:text-[14px] max-sm:leading-normal dark:text-white"
      >
        {{ item.content }}
      </p>
    </template>
  </UAccordion>
</template>

<script setup>
const items = [
  {
    label: " Apa saja layanan yang ditawarkan oleh Monro MotoClub?",

    content:
      "Monro MotoClub menawarkan berbagai layanan perawatan dan perbaikan motor, termasuk servis berkala, perbaikan mesin, penggantian oli, perbaikan rem, dan banyak lagi. Kami juga menjual berbagai sparepart asli dan berkualitas tinggi untuk semua jenis motor.",
  },
  {
    label: "Bagaimana cara memesan sparepart di Monro MotoClub?",
    content:
      "Anda dapat memesan sparepart melalui website kami, langsung datang ke bengkel, atau menghubungi tim layanan pelanggan kami untuk bantuan lebih lanjut. Kami akan memastikan sparepart yang Anda butuhkan tersedia dan siap untuk dipasang.",
  },
  {
    label: " Apakah saya perlu membuat janji temu untuk servis motor?",
    content:
      "Kami sangat menyarankan Anda untuk membuat janji temu agar kami dapat melayani Anda dengan lebih baik dan cepat. Namun, kami juga melayani pelanggan yang datang tanpa janji temu, tergantung ketersediaan waktu.",
  },
];
</script>

<style scoped></style>
