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
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10 px-4">
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#6366f1] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">SOFTWARE DEVELOPMENT</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Ojeeco Global excels in crafting innovative software solutions tailored to meet specific business needs. Our expert developers harness the latest technologies, ensuring scalable, efficient, and future-ready applications that drive productivity and enhance overall business performance.</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#f43f5e] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">SALES STRATEGIES</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Elevate your sales game with Ojeeco's proven strategies. Our sales experts employ data-driven approaches, market insights, and tailored methodologies to boost revenue, maximize market penetration, and establish a lasting competitive edge in your industry</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>
      </div>
       <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#f97316] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">LEAN MANUFACTURING</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Ojeeco optimizes manufacturing processes, implementing lean principles to enhance efficiency and reduce waste. Streamlined workflows and continuous improvement methodologies ensure cost-effectiveness while maintaining high-quality standards, allowing businesses to thrive in a competitive global market.</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#6366f1] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">SOFTWARE DEVELOPMENT</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Ojeeco Global excels in crafting innovative software solutions tailored to meet specific business needs. Our expert developers harness the latest technologies, ensuring scalable, efficient, and future-ready applications that drive productivity and enhance overall business performance.</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>
      </div>
      <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#f43f5e] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">SALES STRATEGIES</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Elevate your sales game with Ojeeco's proven strategies. Our sales experts employ data-driven approaches, market insights, and tailored methodologies to boost revenue, maximize market penetration, and establish a lasting competitive edge in your industry</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>
      </div>
       <div class="max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#f97316] px-2 py-10 rounded-xl">
        <h2 class="text-xl text-white font-semibold mb-2">LEAN MANUFACTURING</h2>
        <p class="mb-4 text-white text-sm hover:text-shadow">Ojeeco optimizes manufacturing processes, implementing lean principles to enhance efficiency and reduce waste. Streamlined workflows and continuous improvement methodologies ensure cost-effectiveness while maintaining high-quality standards, allowing businesses to thrive in a competitive global market.</p>
        <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>
      </div>
    </div>
  </div>
</template>
