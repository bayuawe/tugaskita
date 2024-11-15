<template>
  <header class="flex justify-between items-center p-6 bg-gray-900 shadow-lg relative z-20">
    <div class="text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-red-400 to-pink-500">
      TugasKita!
    </div>

    <!-- Mobile Toggle Button -->
    <div class="md:hidden z-30">
      <button type="button" class="block focus:outline-none hover:opacity-80 transition-opacity"
        @click="isMenuOpen = !isMenuOpen">
        <span v-if="!isMenuOpen" class="text-emerald-400">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
          </svg>
        </span>
        <span v-else class="text-emerald-400">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </span>
      </button>

      <!-- Mobile Menu -->
      <nav :class="[
        'fixed inset-0 z-20 flex flex-col justify-center items-center bg-gray-900/95 backdrop-blur-sm transition-all duration-300 ease-in-out',
        isMenuOpen ? 'opacity-100 visible' : 'opacity-0 invisible'
      ]">
        <ul class="flex flex-col justify-center items-center space-y-8">
          <li v-for="item in menu" :key="item.name">
            <a :href="item.href"
              class="block text-emerald-400 text-2xl font-medium hover:text-emerald-300 hover:scale-110 transition-all"
              @click="scrollToSection(item.href)">
              {{ item.name }}
            </a>
          </li>
        </ul>
      </nav>
    </div>

    <!-- Desktop Menu -->
    <nav class="hidden md:block">
      <ul class="flex items-center space-x-8">
        <li v-for="item in menu" :key="item.name">
          <a :href="item.href"
            class="text-emerald-400 text-lg font-medium hover:text-emerald-300 hover:-translate-y-0.5 transition-all"
            @click="scrollToSection(item.href)">
            {{ item.name }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const isMenuOpen = ref(false);
const menu = ref([
  { name: "Home", href: "#home" },
  { name: "About", href: "#about" },
  { name: "How To Orders", href: "#services" },
  { name: "Orders", href: "#contact" },
]);

const scrollToSection = (href) => {
  isMenuOpen.value = false;
  // Tambahkan logika scrolling di sini jika diperlukan
}
</script>
