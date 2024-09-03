<template>
  <section>
    <HomeCarouselTravel />
    <section class="mt-16">
      <NuxtMarquee
        :gradient="true"
        gradient-color="#f7f7f7"
        auto-fill
        class="flex"
        :loop="0"
      >
        <div v-for="sponsor in marqueeimg" :key="sponsor.id" class="mx-8">
          <img
            :src="sponsor.img"
            alt=""
            class="h-16 grayscale transition-all duration-300 hover:grayscale-0"
          />
        </div>
      </NuxtMarquee>
    </section>
    <section class="mt-24 grid grid-cols-2 text-dark-50">
      <div class="">
        <img
          src="https://img.freepik.com/free-photo/male-mechanics-working-together-car-shop_23-2150376968.jpg?t=st=1725363275~exp=1725366875~hmac=b255ba377c593ba7512e949bd1e775b7a6017e080c48bb1d9a2e96791cedae84&w=996"
          alt=""
          class="mx-auto w-[80%] rounded-md border-4 border-white"
        />
      </div>
      <div class="my-auto mr-12">
        <p
          class="w-fit rounded-full bg-yellow-100 px-4 py-1 text-xs font-semibold uppercase text-yellow-500"
        >
          auto repair
        </p>
        <h1 class="text-4xl font-semibold leading-normal">
          MONRO motoclub and autoservices
        </h1>
        <p class="text-dark-200">
          Monro Motoclub adalah bengkel otomotif terpercaya yang telah melayani
          pelanggan dengan perbaikan dan perawatan kendaraan berkualitas selama
          bertahun-tahun. Terletak di lokasi strategis, Monro Motoclub
          menawarkan berbagai layanan, mulai dari perawatan rutin hingga
          perbaikan kompleks untuk semua jenis kendaraan, termasuk mobil dan
          truk.
        </p>
        <ButtonPrimary
          to="/produk"
          styled="bg-mainn-50 text-lg mt-4 rounded-sm w-fit"
          >Produk Kami</ButtonPrimary
        >
      </div>
    </section>
    <section class="mt-16 flex flex-col gap-8">
      <div class="ml-2 flex flex-col items-center self-center">
        <h1 class="text-[42px] font-semibold text-yellow-500">Produk Kami</h1>
        <p class="text-dark-200">
          Berbagai produk dan layanan di MONRO autoservices
        </p>
      </div>
      <div class="flex flex-wrap justify-evenly gap-4">
        <CardTravel
          v-for="(item, index) in data.slice(0, 4)"
          :key="index"
          :image="`http://localhost:8080/bengkelbe/${item.image.file_path}`"
          :title="item.produk_name"
          :desc="item.description"
          :rating="4.8"
          :price="formatRupiah(item.price)"
          :maps="item.maps"
          :to="`/produk/${item.id}`"
        />
      </div>
    </section>

    <section class="mt-16 flex flex-col gap-8">
      <h1 class="styled h1">Tentang Kami</h1>
      <HomeFaqAccordion />
    </section>
  </section>
</template>

<script setup>
import { formatRupiah } from "@/utils/formatCurrency";
const marqueeimg = [
  {
    id: 1,
    img: "https://www.carlogos.org/tire-logos/dunlop-logo-2200x500.png",
  },
  {
    id: 2,
    img: "https://seeklogo.com/images/M/michelin-logo-34273FA58D-seeklogo.com.png",
  },
  {
    id: 3,
    img: "https://w7.pngwing.com/pngs/41/131/png-transparent-dhl-hd-logo.png",
  },
  {
    id: 4,
    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT0ReIH8t-mIvXGWypKX7T5KiWhZaxmBHoj3g&s",
  },
  {
    id: 5,
    img: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/66/Ducati_red_logo.PNG/723px-Ducati_red_logo.PNG",
  },
  {
    id: 6,
    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrTZ3ZTXTIejqldmq8jWHkyZ6qriFXWCvgXw&s",
  },
  {
    id: 7,
    img: "https://i.pinimg.com/originals/cb/49/b8/cb49b8cbdf96d32e22e434f856649e5d.png",
  },
  {
    id: 8,
    img: "https://logodownload.org/wp-content/uploads/2016/11/formula-1-logo-5-2.png",
  },
];

const apiUrl = "https://8744-110-138-93-77.ngrok-free.app/bengkelbe/dataproduk";
// fetch data langsung
const { data, error } = await useFetch(apiUrl);
if (error.value) {
  console.error("Error fetching data:", error.value);
}
console.log(data);
</script>

<style scoped>
nav {
  li {
    color: rgb(255, 255, 255);
  }
}
.style {
  @apply w-max border-b-[3px] border-transparent px-12 py-6 hover:border-green-600 max-md:px-4 max-md:text-[12px];
}
.styled.h1 {
  @apply text-center text-3xl font-bold text-yellow-500 max-sm:text-xl;

  span {
    @apply italic;
  }
}
</style>
import type { UButton } from '#build/components'; import type { UButton } from
'#build/components';
