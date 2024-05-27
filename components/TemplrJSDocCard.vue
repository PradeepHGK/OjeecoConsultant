<template>
    <p class="flex justify-center font-semibold text-2xl py-10">OUR USP</p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4 xl:gap-8 pb-12 px-4">
    
      <div v-for="(card, index) in data" :key="index" class="flex w-full relative text-white overflow-hidden rounded-3xl shadow-lg">
        <div :class="`flex w-full md:flex-col bg-gradient-to-br ${card.bgFrom} ${card.bgTo}`">
          <div class=" flex flex-col items-start relative z-10 p-6 xl:p-8">
  
            <div class="flex justify-center items-center w-full">
              <img :src="card.logo" class="w-28">
            </div>
            <h2 class="text-xl font-semibold mb-2 text-black">{{ card.heading }}</h2>
            <p :class="`mb-4 ${card.textColor} text-sm hover:text-shadow`">
            {{ card.paragraph }}
            </p>
          
            
           
            
            <!--<a :href="card.link" :class="`mt-auto ${card.buttonColor} text-shadow hover:bg-opacity-75 transition-colors duration-200 rounded-xl font-semibold py-2 px-4 inline-flex`">
              {{ card.buttonText }}
            </a>-->
          </div>
          <div class="relative hidden sm:block"></div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 h-20 hidden sm:block" :style="gradientStyle(card)"></div>
      </div>
      <div class="w-full flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
        <div class="flex justify-center items-center w-full">
          <img src="/client.png" alt="" class="w-28">
        </div>
         <h2 class="text-xl text-black font-semibold mb-2">CLIENT-CENTRIC APPROACH</h2>
         <p class="mb-4 text-black text-sm hover:text-shadow">Ojeeco prioritizes long-term client relationships, emphasizing personalized client management. Our team is dedicated to understanding each client's unique needs, fostering collaboration, and delivering solutions that meet and exceed expectations.</p>
         <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>-->
      </div>
      <div class="w-full flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
        <div class="flex justify-center items-center w-full">
          <img src="/innovation.png" class="w-28">
        </div>
         <h2 class="text-xl text-black font-semibold mb-2">INNOVATION AT THE CORE</h2>
         <p class="mb-4 text-black text-sm hover:text-shadow">With a commitment to staying at the forefront of technological advancements, Ojeeco integrates innovative solutions into its services. Whether it's software development or lean manufacturing, clients benefit from cutting-edge technologies that drive efficiency and competitiveness.</p>
         <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>-->
      </div>
    </div>
      <p class="px-4 pt-10">By combining global expertise, a comprehensive service spectrum, strategic partnerships, a client-centric approach, and a commitment to innovation, Dytrone Global Limited positions itself as the go-to partner for businesses seeking unparalleled solutions for global success</p>
  </template>
  
  <script setup>
  import { computed } from 'vue';
  
  const props = defineProps({
    data: Array,
  });
  
  const gradientStyle = (card) => {
    return `background: linear-gradient(to top, ${card.bgFrom}, rgba(${card.bgFrom}, 0));`;
  };
  </script>
  
  <style>
  /* You can add additional styles if needed */
  
  </style>