<script setup>
import { parseMarkdown } from '@nuxtjs/mdc/runtime';
import _ from 'lodash';


const data = await $fetch(`${useRuntimeConfig().public.API_BASE_URL}/posts?select=id,title,created_at,cover_image,article_type,abstract,published&article_type.eq=Blog&title.neq=&order=created_at desc&limit=6`);
const articlesContent = ref([]);
const filteredArticles = ref([]);


if (data && _.isArray(data.data)) {
  articlesContent.value = data.data;
  filteredArticles.value = _.orderBy(articlesContent.value, (article) => new Date(_.get(article, 'created_at')), 'desc');
}
</script>

<template>
  <div class="pb-10">
    <div class="px-6 py-6 flex justify-center">
      <div class="flex flex-row items-center space-x-3 py-10 pb-3">
        <Icon name="mdi:star-three-points-outline" size="2em" class="text-black" />
        <h2 class="text-4xl font-semibold text-black">OUR SERVICES</h2>
      </div>
    </div>
    <!--<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <template v-for="item in filteredArticles" :key="item.title">
        <article class="group border m-2 overflow-hidden rounded-2xl shadow-sm text-zinc-700">
          <a :href="`/blog/${useNuxtApp().$s.slugify(item.title)}`">
            <img class="lg:h-48 md:h-36 w-full object-cover object-center rounded-t-2xl shadow-lg group-hover:scale-[1.02] transition-all duration-500" :src="item.cover_image" :alt="_.startCase(title)" />
            <div class="px-3 pb-4">
              <div class="text-black pt-3 pb-2">
                <div class="flex items-center">
                  <LogoDate />
                  {{ $dayjs(item.created_at).format('DD-MMM-YYYY') }}
                </div>
              </div>
              <h2 class="text-xl font-semibold text-black pb-1 group-hover:text-sky-700">
                {{ _.startCase(title) }}
              </h2>
              <p class="text-ellipsis line-clamp-2 text-base">
                {{ item.abstract }}
              </p>
              <div class="flex group-hover:underline text-sky-700 items-center py-2">
                <p>Read More</p>
                <LogoArrow />
              </div>
            </div>
          </a>
        </article>
      </template>
      
    </div>-->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
        <div class="flex justify-center items-center w-full mb-4">
          <img src="public/sd.png" alt="" class="w-16">
        </div>
        <h2 class="text-xl text-black font-semibold mb-2">SOFTWARE DEVELOPMENT</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">Harnessing the power of cutting-edge technologies, we craft tailored software solutions to elevate your business operations.</p>
        <a href="/services" class="text-red-800">Read More</a>
      </div>
       <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
         <div class="flex justify-center items-center w-full mb-4">
        <img src="public/sales.png" alt="" class="w-16">
      </div>
        <h2 class="text-xl text-black font-semibold mb-2">SALES</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">Our seasoned professionals excel in driving sales strategies that propel businesses toward unprecedented growth..</p>
         <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>-->
         <a href="/services" class="text-red-800">Read More</a>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
         <div class="flex justify-center items-center w-full mb-4">
        <img src="public/leanmanagement.png" alt="" class="w-16">
        </div>
        <h2 class="text-xl text-black font-semibold mb-2">LEAN MANUFACTURING</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">We optimize manufacturing processes, ensuring efficiency and cost-effectiveness without compromising quality</p>
        <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>-->
        <a href="/services" class="text-red-800">Read More</a>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
         <div class="flex justify-center items-center w-full mb-4">
        <img src="public/userengagement.png" alt="" class="w-16">
      </div>
        <h2 class="text-xl text-black font-semibold mb-2">CLIENT ACQUISITION</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">Dytrone Global Limited excels in connecting businesses with clients, facilitating growth and expansion on a global scale.</p>
        <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>-->
        <a href="/services" class="text-red-800">Read More</a>
      </div>
       <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
         <div class="flex justify-center items-center w-full mb-4">
        <img src="public/projectmanagement.png" alt="" class="w-16">
        </div>
        <h2 class="text-xl text-black font-semibold mb-2">PROJECT MANAGEMENT</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">Our adept project management team ensures seamless execution, meeting deadlines and exceeding expectations.</p>
        <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>-->
        <a href="/services" class="text-red-800">Read More</a>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl shadow-lg">
         <div class="flex justify-center items-center w-full mb-4">
        <img src="public/crm.png" alt="" class="w-16">
        </div>
        <h2 class="text-xl text-black font-semibold mb-2">CLIENT RELATIONSHIP MANAGEMENT</h2>
        <p class="mb-4 text-black text-sm hover:text-shadow">Our adept project management team ensures seamless execution, meeting deadlines and exceeding expectations.</p>
        <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>-->
        <a href="/services" class="text-red-800">Read More</a>
      </div>
    </div>
  </div>
</template>
