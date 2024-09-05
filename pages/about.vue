<template>
  <main class="mt-12">
    <section>
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/6/66/2008-09-24_Monro_Muffler_and_Brake_in_Durham.jpg"
        alt=""
        class="mx-auto my-8 w-[600px] rounded-lg"
      />
      <div class="content-wrapper">
        <h1 class="title mb-4 text-center text-mainn-50">
          Sejarah MONRO motoclub
        </h1>
        <p>
          Monro MotoClub didirikan pada tahun 2005 oleh sekelompok penggemar
          otomotif yang memiliki visi untuk menciptakan tempat berkumpulnya para
          pemilik motor yang menginginkan layanan servis berkualitas dan
          komunitas yang solid. Berawal dari sebuah bengkel kecil di pusat kota,
          Monro MotoClub dengan cepat berkembang berkat komitmen terhadap
          kualitas, kejujuran, dan kepuasan pelanggan. Sejak awal, Monro
          MotoClub telah berfokus pada penyediaan layanan servis motor yang
          menyeluruh, mulai dari perawatan rutin hingga perbaikan besar. Dengan
          berjalannya waktu, kami juga memperluas layanan kami dengan
          menambahkan penjualan sparepart asli dan berkualitas tinggi untuk
          berbagai jenis motor. Ini memungkinkan pelanggan kami untuk
          mendapatkan semua kebutuhan perawatan motor di satu tempat. Pada tahun
          2010, Monro MotoClub memperluas jaringan bengkelnya ke beberapa lokasi
          di kota, memungkinkan lebih banyak pengendara motor untuk merasakan
          layanan kami yang terpercaya. Kami juga mulai mengadakan berbagai
          acara komunitas, seperti touring dan gathering, yang semakin
          mempererat hubungan dengan pelanggan dan membentuk komunitas pecinta
          motor yang kuat. Kini, Monro MotoClub dikenal sebagai salah satu
          bengkel motor terkemuka yang mengedepankan inovasi, layanan pelanggan
          yang unggul, dan kualitas terbaik dalam setiap layanan yang diberikan.
          Dengan tim teknisi yang terus diperbarui dengan pengetahuan dan
          teknologi terbaru, kami terus berkomitmen untuk menjaga dan
          meningkatkan performa kendaraan pelanggan kami. Monro MotoClub tidak
          hanya sekadar bengkel, tetapi juga sebuah komunitas yang tumbuh
          bersama dengan para pengendara motor. Seiring dengan perkembangan
          zaman, kami terus berinovasi dan beradaptasi untuk memenuhi kebutuhan
          pelanggan dengan menyediakan layanan online, program keanggotaan, dan
          penawaran khusus yang memberikan nilai tambah bagi para anggota kami.
        </p>
      </div>
    </section>
    <!-- looping data artikel kelebihan perusahaan -->
    <section class="mt-16 flex flex-col gap-4">
      <h1 class="mb-8 text-center text-3xl font-bold uppercase text-mainn-50">
        Kelebihan MONRO Motoclub
      </h1>
      <div class="content-wrapper" v-for="item in datakelebihan" :key="item.id">
        <h1 class="title-kelebihan">{{ item.title }}</h1>
        <p>{{ item.description }}</p>
      </div>
    </section>
    <!-- loop data visi misi -->
    <section class="mt-16 flex flex-col gap-4">
      <h1 class="text-center text-3xl font-bold uppercase text-mainn-50">
        Visi dan Misi
      </h1>
      <p class="text-md mx-24 mb-8 text-center text-zinc-400">
        "Menjadi bengkel motor terdepan yang dikenal atas keunggulan dalam
        kualitas layanan, inovasi, dan kontribusi positif dalam membangun
        komunitas pengendara motor yang solid dan terpercaya."
      </p>
      <div class="content-wrapper" v-for="item in datavisimisi" :key="item.id">
        <h1 class="title-kelebihan">{{ item.title }}</h1>
        <p>{{ item.description }}</p>
      </div>
    </section>
    <section class="mt-16 flex flex-col gap-8">
      <h1 class="text-center text-3xl font-bold uppercase text-mainn-50">
        Client Kami
      </h1>

      <NuxtMarquee
        :gradient="true"
        gradient-color="#f7f7f7"
        auto-fill
        class="my-8 flex"
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
    <CardTravelSkeleton
      image="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTWN8hLKJungcUipWLReON9fse4yZcyB0rzNw&s"
    />
  </main>
</template>

<script setup>
const datakelebihan = [
  {
    id: 1,
    title: "Teknisi Profesional dan Berpengalaman",
    description:
      "Monro MotoClub didukung oleh tim teknisi yang terlatih dan bersertifikat, dengan pengalaman luas dalam menangani berbagai jenis motor. Keahlian mereka memastikan setiap perbaikan dilakukan dengan presisi dan ketelitian tinggi.",
  },
  {
    id: 2,
    title: "Sparepart Berkualitas",
    description:
      "Kami menyediakan sparepart asli dan berkualitas tinggi dari merek-merek ternama. Setiap sparepart yang kami jual telah melalui proses seleksi ketat untuk memastikan kompatibilitas dan kinerja terbaik.",
  },
  {
    id: 3,
    title: "Jaringan dan Komunitas Kuat",
    description:
      "Monro MotoClub tidak hanya sekadar bengkel, tetapi juga pusat komunitas bagi para pengendara motor. Kami rutin mengadakan acara komunitas seperti touring, gathering, dan workshop yang mempererat hubungan antara pelanggan dan memperkaya pengalaman mereka sebagai pengendara.",
  },
  {
    id: 4,
    title: "Layanan Darurat dan Towing",
    description:
      "Kami menyediakan layanan darurat dan towing untuk membantu pelanggan yang mengalami masalah di jalan. Layanan ini tersedia 24/7, memastikan Anda selalu mendapatkan bantuan kapan pun dibutuhkan.",
  },
];
const datavisimisi = [
  {
    id: 1,
    title: "Memberikan Layanan Berkualitas Tinggi",
    description:
      "Mengutamakan kualitas dalam setiap layanan yang kami berikan, mulai dari perawatan rutin hingga perbaikan kompleks, dengan standar profesionalisme yang tinggi.",
  },
  {
    id: 2,
    title: "Menyediakan Sparepart Berkualitas",
    description:
      "Menyediakan dan memastikan ketersediaan sparepart asli dan berkualitas tinggi untuk semua jenis motor, sehingga pelanggan kami dapat selalu mengandalkan performa kendaraan mereka.",
  },
  {
    id: 3,
    title: "Membangun Komunitas Pengendara",
    description:
      "Membentuk dan memperkuat komunitas pengendara motor melalui berbagai kegiatan seperti event touring, gathering, dan edukasi otomotif, serta menjalin hubungan yang erat dengan pelanggan.",
  },
  {
    id: 4,
    title: "Menjaga Kepercayaan dan Kepuasan Pelanggan",
    description:
      "Mengedepankan transparansi, kejujuran, dan pelayanan pelanggan yang ramah untuk membangun dan mempertahankan kepercayaan serta kepuasan pelanggan.",
  },
];
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
</script>
<style scoped>
.hide-scrollbar {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
.hide-scrollbar::-webkit-scrollbar {
  display: none; /* Safari and Chrome */
}
.content-wrapper {
  @apply flex flex-col gap-2;
  p {
    @apply text-[18px] leading-relaxed;
  }
}
.title {
  @apply text-3xl font-bold uppercase;
}
.title-kelebihan {
  @apply text-2xl font-bold uppercase;
}
</style>
