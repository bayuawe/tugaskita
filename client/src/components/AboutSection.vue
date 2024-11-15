<template>
  <section class=" py-12 px-4 sm:px-6 lg:px-8" id="about">
    <div class="max-w-7xl mx-auto">
      
      <div class="text-center">
        <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
          About Us
        </h2>
        <p class="mt-4 text-xl text-gray-100">
          Solusi terpercaya untuk membantu Anda menyelesaikan skripsi dengan cepat dan berkualitas
        </p>
      </div>

      <!-- Features Section -->
      <div class="mt-20">
        <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-3 md:gap-x-8 md:gap-y-10">
          <div v-for="feature in features" :key="feature.id" class="relative">
            <dt>
              <div class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                <img :src="feature.icon" alt="Feature icon" class="h-6 w-6" aria-hidden="true" />
              </div>
              <p
                class="ml-16 text-lg leading-6 font-medium bg-gradient-to-r from-red-400 to-pink-500 bg-clip-text text-transparent lg:text-xl">
                {{ feature.name }}
              </p>

            </dt>
            <dd class="mt-2 ml-16 text-base text-gray-300">
              {{ feature.description }}
            </dd>
          </div>
        </dl>
      </div>

      <!-- Testimonial Section -->
      <div class="mt-20">
        <blockquote class="mt-10">
          <div class="max-w-3xl mx-auto text-center text-2xl leading-9 font-medium text-gray-500">
            <p>
              "TugasKita! telah membantu saya menyelesaikan skripsi tepat waktu dengan hasil yang memuaskan. Terima
              kasih
              atas bantuan dan bimbingannya!"
            </p>
          </div>
          <footer class="mt-8">
            <div class="md:flex md:items-center md:justify-center">
              <div class="md:flex-shrink-0">
                <img class="mx-auto h-10 w-10 rounded-full"
                  src="https://img.icons8.com/?size=100&id=Chgb7mhcx0Yj&format=png&color=000000" alt="Foto Mahasiswa" />
              </div>
              <div class="mt-3 text-center md:mt-0 md:ml-4 md:flex md:items-center">
                <div class="text-base font-medium text-gray-100">Ferdi Hadi Putra</div>
                <svg class="hidden md:block mx-1 h-5 w-5 text-indigo-600" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M11 0h3L9 20H6l5-20z" />
                </svg>
                <div class="text-base font-medium text-gray-500">Mahasiswa Universitas Muhammadiyah Riau</div>
              </div>
            </div>
          </footer>
        </blockquote>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const features = ref([
  {
    id: 1,
    name: 'Kualitas Terjamin',
    description: 'Tim kami terdiri dari lulusan terbaik dan berpengalaman dalam penulisan skripsi.',
    icon: "https://img.icons8.com/?size=100&id=SwvDja4ryubi&format=png&color=000000",
  },
  {
    id: 2,
    name: 'Tepat Waktu',
    description: 'Kami berkomitmen untuk menyelesaikan skripsi Anda sesuai dengan deadline yang ditentukan.',
    icon: "https://img.icons8.com/?size=100&id=E8UDNc2M7twd&format=png&color=000000",
  },
  {
    id: 3,
    name: 'Bimbingan Komprehensif',
    description: 'Kami tidak hanya menulis, tapi juga membimbing Anda dalam memahami skripsi Anda.',
    icon: "https://img.icons8.com/?size=100&id=xM5NpnNBYbws&format=png&color=000000",
  },
]);
</script>
