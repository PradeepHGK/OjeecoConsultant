<template>
  <div class="md:py-12 sm:py-24 px-4 lg:px-0 rounded-3xl rounded-t-none -mt-4 relative text-gable-green bg-white" style="z-index: 6">
    <div class="m-auto max-w-screen-xl">
      <div class="md:flex justify-center py-20">
            <h2 class="px-14 text-lg md:text-3xl text-zinc-600 font-bold w-full mb-4 md:mb-0 lg:w-6/12">NEED A QUOTE ? CALL US NOW..</h2>
            <a class="px-32 text-lg inline-flex md:text-2xl font-normal text-gable-green whitespace-nowrap items-center hover:text-blurple" href="#">+245720829302</a>
          </div>
      
    </div>
  </div>
</template>
<script setup>
import * as heroIcons from '@heroicons/vue/20/solid';
const props = defineProps({
  api_end_point: {
    type: String,
    required: true,
  },
});

let path = props.api_end_point != undefined ? props.api_end_point : '/configs/tech-stack';


const result = await fetch(`https://www.senthilsweb.com/configs/tech-stack.json`, {
  method: 'get',
});

const links = await result.json()

</script>
<style>
@keyframes carouselspin {
  0% {
    transform: translateX(0);
  }

  to {
    transform: translateX(-100%);
  }
}
</style>
