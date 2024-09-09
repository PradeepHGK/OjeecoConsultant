<template>
  <main class="mx-auto mt-8 max-w-7xl px-6 lg:mt-16 sm:px-0 lg:max-w-7xl mx-auto">
    <!-- <div class="w-full max-w-4xl mx-auto flex flex-col items-center relative z-10 p-4 xl:p-6 bg-gray-100 px-2 py-8 rounded-xl shadow-lg mb-10">
      <p class="mb-2 text-black text-sm hover:text-shadow">"Empowering Businesses, Enabling Growth: Ojeeco Consulting - Your Catalyst for Global Success."</p>
      <p class="mb-2 text-black text-sm hover:text-shadow">"Seamless Solutions, Global Connections: Ojeeco Consulting Limited - Where Opportunities Meet Expertise."</p>
      <p class="mb-2 text-black text-sm hover:text-shadow">"Innovate, Expand, Excel: Ojeeco Consulting - Your Partner in Unleashing Worldwide Business Potential."</p>
    </div> -->

    <!-- <div class="relative overflow-hidden">
    <swiper :options="swiperOptions" class="swiper-container">
      <swiper-slide v-for="(slide, index) in slides" :key="index">
        <div class="relative w-full h-full">
          <img :src="slide.image" alt="Banner Image" class="w-full h-full object-cover" />
          <div class="absolute inset-0 flex items-center justify-center">
            <blockquote class="bg-black bg-opacity-50 text-white p-4 rounded-lg">
              <p class="text-xl">{{ slide.quote }}</p>
            </blockquote>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div> -->
    <div class="lg:grid lg:grid-cols-12 lg:gap-8">
      <div class="sm:text-center md:mx-auto md:max-w-2xl lg:col-span-6 lg:text-left">
        <h1>
          <span class="mt-1 p-1 block text-4xl space-y-6 font-bold tracking-tight sm:text-2xl xl:text-4xl">
            <span class="block text-transparent bg-clip-text bg-gradient-to-r from-green-400 via-blue-500 to-purple-500">{{ hero.title.primary }} - {{hero.title.secondary}}</span>
            <!-- <span class="block text-transparent bg-clip-text bg-gradient-to-r from-green-400 via-blue-500 to-purple-500">{{ hero.title.secondary }}</span> -->
          </span>
        </h1>
        <p class="mt-3 text-base text-gray-700 sm:mt-5 sm:text-sm lg:text-lg xl:text-lg">{{ hero.description }}</p>

        <!--<div class="mt-10 sm:flex sm:justify-center lg:justify-start">
          <div class="hidden md:flex md:items-center md:space-x-6">
            <NuxtLink to="#" @click="useNuxtApp().$bus.$emit(`${hero.button.primary.click_event}`)"
              class="px-5 py-2 text-md ring-2 hover:ring-2 text-white rounded-full transition-all duration-300"
              :class="[`bg-[${useThemeStore().palette('500')}]`, `hover:bg-[${useThemeStore().palette('700')}]`, `ring-[${useThemeStore().palette('500')}]`]">
              {{ hero.button.primary.text }}</NuxtLink>
            <NuxtLink to="#" @click="useNuxtApp().$bus.$emit(`${hero.button.secondary.click_event}`)"
              class="px-5 py-2 text-md border border-transparent bg-white hover:text-white ring-2 rounded-full transition-all duration-300"
              :class="[`text-[${useThemeStore().palette('500')}]`, `hover:bg-[${useThemeStore().palette('700')}]`, `ring-[${useThemeStore().palette('500')}]`]">
              {{ hero.button.secondary.text }}</NuxtLink>
          </div>
        </div>-->
      </div>
      <div class="relative mt-12 sm:mx-auto sm:max-w-lg lg:col-span-6 lg:mx-0 lg:mt-0 lg:flex lg:max-w-none lg:items-center">
        <div class="relative mx-auto w-full rounded-lg lg:max-w-md">
          <template v-if="hero.video.url && hero.video.weight > hero.image.weight">
            <VideoPlayer :src="hero.video.url" />
          </template>
          <template v-else-if="hero.image.url">
            <span class="sr-only">{{ hero.image.alt }}</span>
            <img class="w-full h-80 md:h-96 object-cover" :src="hero.image.url" :alt="hero.image.alt" />
          </template>
          <template v-else> no image </template>
        </div>
      </div>
    </div>
      <!-- <div class="w-full max-w-lg mx-auto flex flex-col items-center relative z-10 p-4 xl:p-6 bg-gray-100 px-6 py-4 rounded-xl shadow-lg mb-10 mt-10"> -->
      <!-- <p class="text-base"><span class="font-semibold mr-1">News / Ad messages</span>Like New Product / ERP release</p> -->
    <!-- </div> -->
  </main>
</template>

<script setup>
const data = await import('~/configs/hero.json');
const hero = data;

// import SwiperCore, { Navigation, Pagination } from 'swiper';
// import { Swiper, SwiperSlide } from 'swiper/vue';
// import 'swiper/swiper-bundle.css';

// SwiperCore.use([Navigation, Pagination]);

// export default {
//   components: {
//     Swiper,
//     SwiperSlide
//   },
//   data() {
//     return {
//       slides: [
//         { image: '/images/banner1.jpg', quote: 'This is a quote for image 1' },
//         { image: '/images/banner2.jpg', quote: 'This is a quote for image 2' },
//         { image: '/images/banner3.jpg', quote: 'This is a quote for image 3' },
//       ],
//       swiperOptions: {
//         loop: true,
//         autoplay: {
//           delay: 5000,
//         },
//         pagination: { clickable: true },
//         navigation: true
//       }
//     }
//   }
// }
</script>

<style scoped>
.swiper-container {
  width: 100%;
  height: 100%;
}
</style>