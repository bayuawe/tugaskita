<template>
  <section class="relative w-full" data-aos="zoom-in-up">
    <div class="absolute top-0 inset-x-0 h-64 flex items-start">
      <div class="h-24 w-2/3 bg-gradient-to-br from-[#570CAC] blur-2xl invinsible opacity-40"></div>
      <div class="h-24 w-2/3 bg-gradient-to-r from-[#670CCF] blur-2xl opacity-40"></div>
    </div>
    <div class="w-full px-5 sm:px-8 md:px-12 lg:px-8 max-w-screen-lg lg:max-w-screen-xl mx-auto relative">
      <div
        class="grid lg:grid-cols-2 gap-10 xl:gap-14 relative pt-24 lg:max-w-none max-w-2xl md:max-w-3xl mx-auto items-center">
        <div class="lg:py-6">
          <div class="text-left lg:text-left">
            <h1 class="pt-4 text-white font-bold text-4xl md:text-5xl lg:text-6xl">
              BINGUNG KERJAIN TUGAS? JADIIN<span
                class="text-transparent bg-clip-text bg-gradient-to-r from-red-400 to-pink-500"> TUGAS KITA </span>
              AJA!
            </h1>
          </div>

          <div class="flex items-center gap-3 pt-9 flex-col sm:flex-row sm:w-max sm:mx-auto lg:mx-0">
            <!-- Button Order -->
            <button
              class="rounded-md border border-transparent py-2 px-4 flex items-center text-center text-sm transition-all text-white hover:bg-gradient-to-r from-red-400 to-pink-500 focus:bg-slate-100 active:bg-slate-100 disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none"
              type="button">
              Order!

              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4 ml-1.5">
                <path fill-rule="evenodd"
                  d="M16.72 7.72a.75.75 0 0 1 1.06 0l3.75 3.75a.75.75 0 0 1 0 1.06l-3.75 3.75a.75.75 0 1 1-1.06-1.06l2.47-2.47H3a.75.75 0 0 1 0-1.5h16.19l-2.47-2.47a.75.75 0 0 1 0-1.06Z"
                  clip-rule="evenodd" />
              </svg>
            </button>

            <button
              class="flex items-center rounded-md bg-gradient-to-tr from-slate-800 to-slate-700 py-2 px-4 border border-transparent text-center text-sm text-white transition-all shadow-sm hover:shadow-lg focus:bg-slate-700 focus:shadow-none active:bg-slate-700 hover:bg-slate-700 active:shadow-none disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none"
              type="button">
              How to order
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-4 h-4 ml-1.5">
                <path fill-rule="evenodd"
                  d="M16.28 11.47a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 0 1-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 0 1 1.06-1.06l7.5 7.5Z"
                  clip-rule="evenodd" />
              </svg>
            </button>
          </div>
        </div>

        <div class="lg:h-full md:flex">
          <div class="flex w-full h-96 min-h-[24rem] lg:min-h-none lg:w-full lg:h-full items-center relative">
            <div
              class="absolute z-0 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-[#570CAC] to-primary blur-2xl">
            </div>
            <div
              class="absolute h-full z-10 p-2 lg:right-3 md:right-40 sm:right-16 rounded-full shadow-lg border-primary">
              <img src="@/assets/images/heroimage.png" alt="hero image" width="500" height="auto" loading="lazy"
                class="w-full h-full rounded-full object-cover">
            </div>
          </div>
        </div>
      </div>
    </div>

  </section>
</template>

<script setup>
import AOS from "aos";
import 'aos/dist/aos';
AOS.init();
</script>
