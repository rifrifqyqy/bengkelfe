<template>
  <div>
    <nav
      class="navbar sticky top-0 z-[999] mt-2 flex items-center justify-between px-24 py-2 transition-all duration-300 max-md:px-8"
    >
      <div class="flex items-center justify-between gap-12">
        <NuxtLink to="/">
          <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQtoHc36Z2CMN9vThk76P2T3XRpNrWAsaQ_Cg&s"
            alt=""
            class="logo w-[180px] transition-all max-md:w-[100px]"
          />
        </NuxtLink>
        <ul
          class="flex gap-8 text-[18px] text-dark-200 max-md:gap-2 max-sm:hidden"
        >
          <li>
            <NuxtLink to="/" :class="styledMenuNav">Beranda</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/produk" :class="styledMenuNav">Produk</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" :class="styledMenuNav">Event</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/artikel" :class="styledMenuNav">Artikel</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" :class="[styledMenuNav]"
              >Tentang Kami</NuxtLink
            >
          </li>
        </ul>
      </div>

      <buttonPrimary
        styled="rounded-sm bg-green-700 px-5 text-[20px] bg-mainn-50 text-light-50 ring-inset ring-green-400 hover:opacity-80 active:ring-2 max-sm:hidden"
      >
        Produk Kami
      </buttonPrimary>
      <button class="hidden max-sm:block" @click="toggleNav">
        <Hamburger fill="fill-green-600" />
      </button>
    </nav>
    <nav
      :class="[
        'nav-mobile',
        { show: isNavVisible },
        'fixed top-[48px] z-50 hidden h-fit w-full -translate-y-[100dvh] bg-white transition-all duration-300 max-sm:block',
      ]"
    >
      <ul class="text-green-600">
        <li>
          <NuxtLink to="/" :class="styledMenuNav">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/our_menu" :class="styledMenuNav">Menu</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/promo" :class="styledMenuNav">Promo</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about" :class="[styledMenuNav]">About</NuxtLink>
        </li>
      </ul>
      <buttonPrimary
        styled="rounded-md mt-4 bg-green-700 max-md:py-2 max-md:text-[16px] px-5 text-yellow-400 ring-inset ring-green-400 hover:opacity-80 active:ring-2 w-full h-fit"
      >
        Order Now
      </buttonPrimary>
    </nav>

    <div class="max-md:4 mx-24 min-h-dvh">
      <slot />
    </div>

    <footer class="mt-16 bg-dark-50">
      <section
        class="grid grid-cols-4 px-24 py-12 text-white max-sm:grid-cols-2 max-sm:px-8 max-sm:py-4"
      >
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQtoHc36Z2CMN9vThk76P2T3XRpNrWAsaQ_Cg&s"
          alt=""
          class="col-span-2 w-[150px] rounded-md bg-light-100 px-4 py-2 max-sm:mb-6 max-sm:w-[150px]"
        />
        <div class="menu-list">
          <h1>Navigation</h1>
          <ul class="mt-2 flex flex-col gap-2">
            <li><NuxtLink to="/">Home</NuxtLink></li>
            <li><NuxtLink to="/produk">Produk</NuxtLink></li>
            <li><NuxtLink to="/about">About Us</NuxtLink></li>
          </ul>
        </div>

        <div class="flex flex-col gap-4 max-sm:mt-4">
          <h1 class="text-xl max-sm:text-[16px]">Contact Us</h1>
          <div class="flex flex-col gap-4">
            <p>email : monro.autoservices@business.com</p>
            <p>phone : +62812882222</p>
          </div>
        </div>
      </section>

      <div
        class="col-span-5 mt-4 flex justify-center bg-dark-100 py-2 max-sm:px-4"
      >
        <h1 class="text-md w-fit text-center text-white max-sm:text-sm">
          © 2024 MONRO Motoclub | All rights reserved. Designed by Rifqy
          Hamdani
        </h1>
      </div>
    </footer>
  </div>
</template>

<!-- el scripto -->
<script setup>
import Hamburger from "~/components/Icons/Hamburger.vue";
import Close from "~/components/Icons/Close.vue";
import { ref } from "vue";
const styledMenuNav =
  "hover:text-mainn-50 transition-all duration-300 hover:border-b-2 border-mainn-100 max-md:text-[16px]";

import { onMounted, onUnmounted } from "vue";

const handleScroll = () => {
  const navbar = document.querySelector(".navbar");
  const logo = document.querySelector(".logo");
  if (window.scrollY > 50) {
    navbar.classList.add("scrolled");
    logo.classList.add("logo-resize");
  } else {
    navbar.classList.remove("scrolled");
    logo.classList.remove("logo-resize");
  }
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});
onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

const isNavVisible = ref(false);

const toggleNav = () => {
  isNavVisible.value = !isNavVisible.value;
};


</script>

<style scoped>
.router-link-active {
  @apply font-semibold text-mainn-50;
}

.scrolled {
  @apply border-b border-light-300 bg-white;
}
.logo-resize {
  @apply scale-75;
}
footer {
  section .menu-list {
    h1 {
      @apply text-[20px] font-semibold max-sm:text-[16px];
    }
    li {
      @apply max-sm:text-[14px];
    }
  }
}
.nav-mobile.show {
  @apply translate-y-0/* or whatever style you need to show the nav */;
}

.nav-mobile {
  @apply px-4 py-8;

  ul {
    @apply flex flex-col items-center justify-center gap-4;
  }
}
.submenu-nav2 {
  @apply flex cursor-pointer flex-col items-center gap-1 px-4 pt-1 transition-all;
}
</style>
