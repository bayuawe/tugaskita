<script setup>
import { defineAsyncComponent } from "vue";
// import Components Asynchronously
const Navbar = defineAsyncComponent(() => import("./components/Navbar.vue"))
const HeroSection = defineAsyncComponent(() => import("./components/HeroSection.vue"))
</script>

<template>
  <div class="bg-gray-900 min-h-screen">

    <Navbar />
    <HeroSection />
  </div>
</template>

<style scoped></style>
