<template>
  <section class="text-white mt-20" id="services">
    <div class="px-4 xl:pl-16">
      <h2 class="text-4xl font-bold text-white mb-4 uppercase">Our Service</h2>
    </div>
    <div
      class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
      <div v-for="service in services" :key="service.id" data-aos="fade-up"
        class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]">
        <div class="mx-auto h-24 text-center xl:h-28 xl:w-28 flex items-center justify-center">
          <div>
            <img :src="service.icon" alt="service icon" class="w-16 h-16 md:w-16 md:h-16">
          </div>
        </div>

        <div class="text-center">
          <h3
            class="pt-8 text-lg font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-red-400 to-pink-500 lg:text-xl">
            {{ service.name }}
          </h3>
          <p class="pt-4 text-sm text-gray-400 group-hover:text-white md:text-base">
            {{ service.description }}
          </p>
        </div>
      </div>
    </div>

  </section>
</template>
<script setup>
import { ref } from "vue";
const services = ref([
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=xM5NpnNBYbws&format=png&color=000000",
    name: "Web Development",
    description: "HTML, CSS, Javascript, Laravel, Code Igniter, dll",
  },
  {
    id: 2,
    icon: "https://img.icons8.com/?size=100&id=9x65MLqCekT5&format=png&color=000000",
    name: "Web Design",
    description: "Design UI/UX",
  },
  {
    id: 3,
    icon: "https://img.icons8.com/?size=100&id=yEzFx4cwLDIh&format=png&color=000000",
    name: "Design",
    description: "Desain Grafis, Poster, Brosur, dll",
  },
  {
    id: 4,
    icon: "https://img.icons8.com/?size=100&id=DVzc1vi8FDJt&format=png&color=000000",
    name: "Tugas",
    description: "Skripsi, Makalah, Pengabdian, dll",
  },
  {
    id: 5,
    icon: "https://img.icons8.com/?size=100&id=SoSfiMmUUOIz&format=png&color=000000",
    name: "Teknologi Informasi",
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quae.",
  },
])
</script>
<style></style>
