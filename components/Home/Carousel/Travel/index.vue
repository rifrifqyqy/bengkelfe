<template>
  <section class="relative">
    <swiper
      :slidesPerView="1"
      :spaceBetween="30"
      :loop="true"
      :pagination="{
        el: '.swiper-pagination2',
        clickable: true,
      }"
      :navigation="{
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      }"
      :autoplay="{
        delay: 3000,
        disableOnInteraction: false,
      }"
      :modules="modules"
      class="mySwiper relative mt-4 flex"
    >
      <section
        class="absolute left-0 top-0 z-20 flex h-full w-full items-center justify-center text-white"
      >
        <div class="text-center">
          <h1 class="text-[54px] font-semibold">
            <span class="text-yellow-500">MONRO </span>Motoclub
          </h1>
          <p class="text-light-400 text-xl">
            Membawa Kendaraan Anda Kembali ke Jalur
          </p>
          <ButtonPrimary to="/produk"styled="bg-mainn-50 text-lg mt-4 w-fit"
            >Lihat Layanan Kami</ButtonPrimary
          >
        </div>
      </section>
      <swiper-slide v-for="slide in slides" :key="slide.id">
        <img :src="slide.imgUrl" class="brightness-[50%]" alt="" />
      </swiper-slide>

      <div class="z-50 w-full">
        <div class="swiper-pagination2"></div>
      </div>
    </swiper>
    <div class="swiper-button-prev btnprev">
      <img src="/images/arrowl.svg" alt="" class="w-[32px]" />
    </div>
    <div class="swiper-button-next btnnext">
      <img src="/images/arrowr.svg" alt="" class="w-[32px]" />
    </div>
  </section>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "./travel.css";
import "swiper/css/pagination";
import "swiper/css/navigation";

// import required modules
import { Pagination, Navigation, Autoplay } from "swiper/modules";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const slides = [
      {
        id: 1,
        imgUrl:
          "https://img.freepik.com/free-photo/car-repair-maintenance-theme-mechanic-uniform-working-auto-service_627829-3918.jpg?t=st=1725353815~exp=1725357415~hmac=81ed2a65fc0c541779cece59e4e623ce4a22f7f94c081f71a81d83d3a5653b5b&w=996",
      },
      {
        id: 2,
        imgUrl:
          "https://img.freepik.com/free-photo/car-service-mechanic-using-vr_482257-76101.jpg?t=st=1725353941~exp=1725357541~hmac=7a32d0a6911e220354d0b5c20d1c0e91d5f438007d42ddb248bad3b2d7eeb2c0&w=1380",
      },
      {
        id: 3,
        imgUrl:
          "https://npr.brightspotcdn.com/dims4/default/d3424a2/2147483647/strip/true/crop/5472x3648+0+0/resize/1760x1174!/format/webp/quality/90/?url=http%3A%2F%2Fnpr-brightspot.s3.amazonaws.com%2Flegacy%2Fsites%2Fwxxi%2Ffiles%2F201811%2Fmonro_new_store_exterior.jpg",
      },
      {
        id: 4,
        imgUrl:
          "https://images.simpletire.com/images/installer-images/2423/1/monro-pittsfield-ma-massachusetts.jpg",
      },
      {
        id: 5,
        imgUrl:
          "https://t4.ftcdn.net/jpg/05/21/93/17/360_F_521931702_TXOHZBa3tLVISome894Zc061ceab4Txm.jpg",
      },
      {
        id: 6,
        imgUrl:
          "https://brightonpanelworks.com.au/wp-content/uploads/2022/05/mechanic-in-overalls-repairing-car-in-auto-repair-2021-08-29-22-51-18-utc-1-1080x675.jpg",
      },
      {
        id: 7,
        imgUrl:
          "https://www.cannonautorepair.com/images/mechanic_with_customer.jpeg",
      },
      {
        id: 8,
        imgUrl:
          "https://www.getac.com/uploads/2023/03/autorepairworkshop_cover.png",
      },
    ];
    return {
      modules: [Pagination, Navigation, Autoplay],
      slides,
    };
  },
};
</script>

<style scoped>
.swiper {
  @apply h-full w-full;
}

.swiper-slide {
  @apply relative h-[400px];
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.swiper-button-prev,
.swiper-button-next {
  cursor: pointer;
  @apply mx-4 h-fit w-fit rounded-full bg-mainn-50 p-2 transition-all active:scale-90;

  &::after {
    @apply hidden;
  }
}
</style>
