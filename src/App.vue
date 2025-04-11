<script setup>
import { defineAsyncComponent } from "vue";
// import Components Asynchronously
const Navbar = defineAsyncComponent(() => import("./components/Navbar.vue"))
const HeroSection = defineAsyncComponent(() => import("./components/HeroSection.vue"))
const ServiceSection = defineAsyncComponent(() => import("./components/ServiceSection.vue"))
const AboutSection = defineAsyncComponent(() => import("./components/AboutSection.vue"))
const OrderSection = defineAsyncComponent(() => import("./components/OrderSection.vue"))
</script>

<template>
  <div class="bg-gray-900 min-h-screen">

    <Navbar />
    <HeroSection />
    <ServiceSection />
    <AboutSection />
    <OrderSection />`
  </div>
</template>

<style scoped></style>
