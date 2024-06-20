<template>
    <NuxtLayout name="landing">
      <div>
        <main class="mx-auto max-w-7xl px-4 mt-16 sm:px-6 lg:px-0">
          <!--<div class="flex items-baseline justify-center border-b border-gray-200 pb-6 pt-8 space-x-3">
            <svg data-v-c3ad5561="" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="icon text-black" width="2em" height="2em" viewBox="0 0 24 24"><path fill="currentColor" d="m12 9.5l1.2 4l2.8 3l-4-.9l-4.1.9l2.8-3l1.3-4m0-6.9l-3 9.8l-7 7.5l10-2.3L22 20l-7-7.5l-3-9.9Z"></path></svg>
            <h2 class="text-4xl font-semibold text-black">Blog Posts</h2>
          </div>-->
          <!--<section aria-labelledby="blogs-heading" class="pb-24 pt-6">
            <h2 id="blogs-heading" class="sr-only">Blogs</h2>
  
            <div class="grid grid-cols-1 gap-x-8 gap-y-10 lg:grid-cols-4">
              blog grid (start)
              <div class="lg:col-span-4">
               <ClientOnly>
                  <div class="flex flex-col lg:grid lg:grid-cols-2 xl:grid-cols-3 gap-5 items-start mb-24">
                    <template v-for="article of paginatedData" :key="article.title">
                      <BlogCard :path="article.title" :title="article.title" :date="article.created_at" :description="article.abstract" :image="article.cover_image" :alt="article.title" :og-image="article.cover_image" :tags="[]" :published="article.published" />
                    </template>
                    <template v-if="data?.length === 0">
                      <BlogEmpty />
                    </template>
                  </div>
                </ClientOnly>
  
               <div class="mt-10 flex items-center justify-center gap-x-6">
                 
                    <div class="flex justify-center items-center space-x-6">
                      <button :disabled="pageNumber <= 1" @click="onPreviousPageClick">
                        <Icon name="mdi:code-less-than" size="30" :class="{ 'text-sky-700': pageNumber > 1 }" />
                      </button>
                      <p>{{ pageNumber }} / {{ totalPage }}</p>
                      <button :disabled="pageNumber >= totalPage" @click="onNextPageClick">
                        <Icon name="mdi:code-greater-than" size="30" :class="{ 'text-sky-700': pageNumber < totalPage }" />
                      </button>
                    </div>
                  </div>
  
               <header class="space-y-1 mt-4">
                  <dl class="flex dark:border-gray-800">
                    <div>
                      <dt @click="onPreviousPageClick" class="inline-flex gap-0.5 justify-center overflow-hidden text-sm font-medium transition rounded-full bg-zinc-100 py-1 px-3 text-zinc-900 hover:bg-zinc-200 dark:bg-zinc-800/40 dark:text-zinc-400 dark:ring-1 dark:ring-inset dark:ring-zinc-800 dark:hover:bg-zinc-800 dark:hover:text-zinc-300 cursor-pointer"><span aria-hidden="true">←</span> Previous</dt>
                      <dd class="mt-1">
                        <a @click="onPreviousPageClick" class="text-base font-semibold text-zinc-900 transition hover:text-zinc-600 dark:text-white dark:hover:text-zinc-300" href="#"> {{ useState('prev_shot_name').value }}</a>
                      </dd>
                    </div>
                    <div class="ml-auto text-center">
                      Added text-center class
                      <div class="inline-flex gap-0.5 justify-center overflow-hidden text-sm font-medium text-zinc-900">Page {{ pageNumber }}/{{ totalPage }}</div>
                      Added this line for "page n/n"
                    </div>
                    <div class="ml-auto text-right">
                      <dt @click="onNextPageClick" class="inline-flex gap-0.5 justify-center overflow-hidden text-sm font-medium transition rounded-full bg-zinc-100 py-1 px-3 text-zinc-900 hover:bg-zinc-200 dark:bg-zinc-800/40 dark:text-zinc-400 dark:ring-1 dark:ring-inset dark:ring-zinc-800 dark:hover:bg-zinc-800 dark:hover:text-zinc-300 cursor-pointer">Next <span aria-hidden="true">→</span></dt>
                      <dd class="mt-1">
                        <a @click="onNextPageClick" class="text-base font-semibold text-zinc-900 transition hover:text-zinc-600 dark:text-white dark:hover:text-zinc-300" href="#">{{ useState('next_shot_name').value }} </a>
                      </dd>
                    </div>
                  </dl>
                </header>
              </div>
  
              blog grid (end)
            </div>
          </section>-->
          <div>
            <p class="flex justify-center font-semibold text-lg pb-2">WE ARE OJEECO CONSULTING LTD</p>
            <p class="flex justify-center font-semibold text-base md:text-2xl pb-4">YOUR GATEWAY TO GLOBAL OPPURTUNITIES</p>
            <p class="text-sm">Welcome to Dytrone Global Limited - Your Gateway to Global Opportunities Dytrone Global Limited, established in 2015, is a distinguished consulting firm specializing in software development, sales, lean manufacturing, client acquisition, project management, and client relationship management. Leveraging extensive experience and a global network, we bridge the gap for companies seeking optimal solutions without maintaining large workforces. Operating at the forefront of technological and economic landscapes, we collaborate with businesses worldwide, particularly in the burgeoning economies of China and India. Our mission is to unlock global opportunities, connect clients with tailored solutions, and facilitate expansion beyond domestic markets. Dytrone Global Limited stands as a beacon of innovation, commitment, and excellence in the realm of international business consultancy.</p>
          </div>
          <div class="md:flex md:justify-evenly py-10">
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-12 xl:p-8 bg-[#6366f1] px-2 py-10 rounded-xl mb-4 md:mb-0">
              <div class="flex justify-center items-center w-full mb-4">
               <img src="/mission.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-white font-semibold mb-2">MISSION</h2>
              <p class="mb-6 text-white text-sm hover:text-shadow">Dytrone Global is committed to empowering businesses by providing comprehensive consulting services. Our mission is to navigate the complexities of international markets, deliver tailored solutions, and forge strategic partnerships. Through innovation, efficiency, and client-centric approaches, we enable our clients to expand globally, realize their potential, and achieve enduring success.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>-->
            </div>
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-[#f43f5e] px-2 py-10 rounded-xl">
              <div class="flex justify-center items-center w-full mb-4">
               <img src="/leadership.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-white font-semibold mb-2">VISION</h2>
              <p class="mb-4 text-white text-sm hover:text-shadow">To be the foremost catalyst for global business success, inspiring innovation and fostering enduring partnerships that transcend borders. Dytrone Global envisions a world where businesses thrive through seamless integration into the global marketplace, leveraging our expertise and network for sustained growth and transformative impact.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>-->
            </div>
          </div>
          <p class="flex justify-center font-semibold text-2xl py-10">GOALS</p>
          <div class="md:flex justify-around md:gap-4">
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl mb-4 md:mb-8 shadow-lg">
              <div class="flex justify-center items-center w-full">
               <img src="/support.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-black font-semibold mb-2">Global Expansion Facilitation</h2>
              <p class="mb-4 text-black text-sm hover:text-shadow">Facilitate the seamless expansion of clients into international markets, primarily focusing on China and India. Establish strategic partnerships with key players in diverse industries to enhance global reach.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>-->
            </div>
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl mb-4 md:mb-8 shadow-lg">
              <div class="flex justify-center items-center w-full">
               <img src="/solution.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-black font-semibold mb-2">Innovation and Technology Leadership</h2>
              <p class="mb-6 text-black text-sm hover:text-shadow">Pioneer innovative solutions in software development, ensuring clients stay ahead in the rapidly evolving technology landscape.Be a thought leader in integrating cutting-edge technologies into business strategies,enhancing efficiency and competitiveness.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>-->
            </div>
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl mb-4 md:mb-8 shadow-lg">
              <div class="flex justify-center items-center w-full">
               <img src="/client.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-black font-semibold mb-2">Client Satisfaction and Long-Term Relationships</h2>
              <p class="mb-4 text-black text-sm hover:text-shadow">Achieve high levels of client satisfaction through personalized service, understanding client needs, and delivering value-driven solutions.Foster long-term relationships with clients, becoming a trusted partner in their growth and success.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-orange-600 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">View Documentation</button>-->
            </div>
          </div>
          <div class="md:flex justify-center md:gap-12">
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl mb-4 md:mb-8 shadow-lg">
              <div class="flex justify-center items-center w-full">
               <img src="/innovation.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-black font-semibold mb-2">Operational Excellence and Lean Practices</h2>
              <p class="mb-4 text-black text-sm hover:text-shadow">Continuously optimize internal operations using lean manufacturing principles to enhance efficiency and reduce costs.Achieve industry-leading standards in project management, ensuring timely and successful execution of client projects.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>-->
            </div>
            <div class="w-full max-w-lg md:max-w-sm flex flex-col items-start relative z-10 p-6 xl:p-8 bg-gray-100 px-2 py-10 rounded-xl mb-4 md:mb-8 shadow-lg">
              <div class="flex justify-center items-center w-full">
               <img src="/crm.png" alt="" class="w-28">
              </div>
              <h2 class="text-xl text-black font-semibold mb-2">Community and Environmental Responsibility</h2>
              <p class="mb-6 text-black text-sm hover:text-shadow">Contribute positively to the communities in which we operate by engaging in socially responsible initiatives.Incorporate environmentally sustainable practices into our operations, aligning with global standards for corporate responsibility.</p>
              <!--<button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-rose-900 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Access Resources</button>-->
            </div>
          </div>
          <div>
            <p class="px-4 pt-10">Dytrone Global Limited is dedicated to achieving these goals, guided by its vision and mission, to
create a lasting impact on the global business landscape.</p>
          </div>
            <div class="w-full max-w-lg mx-auto flex flex-col items-center relative z-10 p-4 xl:p-6 bg-gray-100 px-2 py-4 rounded-xl shadow-lg mb-10 mt-10">
      <p class="flex justify-center text-base"><span class="font-semibold mr-1">Team</span>- To be provided by the client</p>
    </div>
          <div class="md:flex justify-center py-20">
            <h2 class="px-14 text-lg md:text-3xl text-zinc-600 font-bold w-full mb-4 md:mb-0 lg:w-6/12">NEED A QUOTE ? CALL US NOW..</h2>
            <a class="px-32 text-lg inline-flex md:text-2xl font-normal text-gable-green whitespace-nowrap items-center hover:text-blurple" href="#">+245720829302</a>
          </div>
        </main>
      </div>
    </NuxtLayout>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { Dialog, DialogPanel, Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems, TransitionChild, TransitionRoot } from '@headlessui/vue';
  import { XMarkIcon } from '@heroicons/vue/24/outline';
  import { ChevronDownIcon, FunnelIcon, MinusIcon, PlusIcon, Squares2X2Icon, Bars3Icon, MagnifyingGlassIcon } from '@heroicons/vue/20/solid';
  import { parseMarkdown } from '@nuxtjs/mdc/runtime';
  import _ from 'lodash';
  import dayjs from 'dayjs';
  
  const mobileFiltersOpen = ref(false);
  const { path } = useRoute();
  //console.log('path=', path);
  
  const savePosts = async (posts) => {
    const API_BASE_URL = useRuntimeConfig().public.API_BASE_URL;
    let i = 1;
    try {
      for (const post of posts) {
        //console.log(post)
        let record = await parseMarkdown(post);
        //console.log("post =" + record.data.title)
        const response = await $fetch(`${useRuntimeConfig().public.API_BASE_URL}/posts`, {
          method: 'POST',
          body: {
            id: i,
            title: useNuxtApp().$s.slugify(record.data.title),
            cover_image: record.data.coverimage,
            article_type: record.data.type,
            abstract: record.data.description,
            article: post,
            created_at: dayjs(record.data.date),
          },
        });
        i++;
        console.log('Saved:', response);
      }
      console.log('All posts saved');
    } catch (err) {
      console.log(err.data);
    }
  };
  
  const data = await $fetch(`${useRuntimeConfig().public.API_BASE_URL}/posts?select=id,title,created_at,cover_image,article_type,abstract,published&article_type.eq=Blog&title.neq=&order=created_at desc`);
  const articlesContent = ref([]);
  const filteredArticles = ref([]);
  
  if (data && _.isArray(data.data)) {
    articlesContent.value = data.data;
  
    filteredArticles.value = _.orderBy(articlesContent.value, (article) => new Date(_.get(article, 'created_at')), 'desc');
  }
  
  //console.log(JSON.stringify(articles))
  const searchPhrase = ref('');
  const elementPerPgae = ref(6);
  const pageNumber = ref(1);
  
  //console.log('filteredArticles = ', JSON.stringify(filteredArticles.value));
  
  const searchData = computed(() => {
    return (
      filteredArticles.value.filter((data) => {
        const lowerTitle = data.title.toLocaleLowerCase();
        //console.log('lowerTitle Match = ', lowerTitle.search(searchPhrase.value) !== -1);
        //console.log('searchPhrase.value = ', searchPhrase.value.toLocaleLowerCase());
        if (lowerTitle.search(searchPhrase.value.toLocaleLowerCase()) !== -1) return true;
        else return false;
      }) || []
    );
  });
  
  //console.log('searchData = ', JSON.stringify(searchData.value));
  
  const paginatedData = computed(() => {
    return (
      searchData.value.filter((data, idx) => {
        const startInd = (pageNumber.value - 1) * elementPerPgae.value;
        const endInd = pageNumber.value * elementPerPgae.value - 1;
  
        if (idx >= startInd && idx <= endInd) return true;
        else return false;
      }) || []
    );
  });
  
  function onPreviousPageClick() {
    if (pageNumber.value > 1) pageNumber.value -= 1;
  }
  
  const totalPage = computed(() => {
    const ttlContent = searchData.value.length || 0;
    const totalPage = Math.ceil(ttlContent / elementPerPgae.value);
    return totalPage;
  });
  
  function onNextPageClick() {
    if (pageNumber.value < totalPage.value) pageNumber.value += 1;
  }
  </script>
  
  <style scoped></style>