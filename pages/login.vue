<template>
  <NuxtLayout name="landing">
    <!--<div class="max-w-sm flex flex-col items-start relative z-10 p-12 xl:p-8 bg-[#6366f1] px-2 py-10 rounded-xl">
            <div class="flex justify-center items-center w-full mb-4">
             <img src="public/mission.png" alt="" class="w-16">
            </div>
            <h2 class="text-xl text-white font-semibold mb-2">MISSION</h2>
            <p class="mb-6 text-white text-sm hover:text-shadow">Ojeeco Global is committed to empowering businesses by providing comprehensive consulting services. Our mission is to navigate the complexities of international markets, deliver tailored solutions, and forge strategic partnerships. Through innovation, efficiency, and client-centric approaches, we enable our clients to expand globally, realize their potential, and achieve enduring success.</p>
            <button class="mt-auto text-white text-shadow hover:bg-opacity-75 transition-colors bg-indigo-800 duration-200 rounded-xl font-semibold py-2 px-4 inline-flex">Explore My Work</button>
          </div>-->
    <div class="px-6 sm:mx-auto sm:w-full sm:max-w-md py-20 bg-violet-900">
          <div class="object-center">
            <p class="text-center text-white font-bold text-2xl">SAY HELLO TO US</p>
            <!--Default logo url configurred thru properties will be set but this can be overridden-->
          </div>

          <p class="mt-6 text-white text-center text-sm font-normal bg-clip-text">
            We are specialists in Project Funding across the world and will give you the enjoyment of our Rapid Service, Copetitive fees and a high client satisfaction rates.</p>
      
          <div class="py-10">
          <p class="font-semibold text-white py-2">ADDRESS</p>
          <p class="text-gray-500">4901 S. Wadsworth Blvd. Unit 11 Littleton,
          CO 80123 USA.</p>
          <p class="font-semibold text-white py-2">PHONE</p>
          <p class="text-gray-500">+245720829302</p>
          <p class="font-semibold text-white py-2">EMAIL</p>
          <p class="text-gray-500">ojeecolimited@outlook.com</p>
          </div>
     
  </div>
  <div class="md:flex justify-center py-20">
          <h2 class="px-16 text-lg md:text-3xl text-zinc-600 font-bold w-full mb-4 md:mb-0 lg:w-6/12">NEED A QUOTE ? CALL US NOW..</h2>
          <a class="px-32 text-lg inline-flex md:text-2xl font-normal text-gable-green whitespace-nowrap items-center hover:text-blurple" href="#">+245720829302</a>
        </div>
  </NuxtLayout>
</template>

<!-- Rest of the script remains unchanged     -->
<script lang="ts" setup>
definePageMeta({
  alias: ['/', '/sign-in'],
});
const supabase = useSupabaseClient();
const user = await supabase.auth.getUser();
const route = useRoute();
const router = useRouter();
const cancelWatch = ref();

console.log('On Sign-in page');




const credentials = ref({
  name: '',
  email: '',
  subject: '',
  phone: '',
  message: ''
});

const userProfile = ref({});

/**
 *
 */
const doSignIn = async () => {
  try {
    const { data, error } = await supabase.auth.signInWithPassword({
      ...credentials.value,
    });

    if (error) {
      // Log the error status code and message
      //presentToast('top', error.message, 'danger');
      alert(error.message)
      console.error('Error:', error.message, 'Status code:', error.status);

      // Check for a 405 status code
      if (error.status === 405) {
        console.error('Method Not Allowed');
        // Handle the 405 error specifically
        // For example, display a specific message to the user
      } else {
        throw error;
      }
    }
    console.log('JWT user===>', JSON.stringify(data.user));


    // Set login session to localstorage
    if (data.user) {
      localStorage.setItem('data:user', JSON.stringify(user.data));
    }
    document.location.href="/docs/getting-started";
    //await navigateTo("/docs/getting-started")

  } catch (error) {
    console.log('error', (error as any)?.message);
    alert((error as any)?.message)
  }
};

</script>
