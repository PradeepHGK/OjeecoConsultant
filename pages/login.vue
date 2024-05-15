<template>
  <NuxtLayout name="landing">
    <div class="sm:mx-auto sm:w-full sm:max-w-md py-20 ml-10">
          <div class="object-center">
            <p class="text-center font-bold text-2xl">SAY HELLO TO US</p>
            <!--Default logo url configurred thru properties will be set but this can be overridden-->
          </div>

          <p class="mt-6 text-center text-xl font-normal bg-clip-text">
            We are specialists in Project Funding across the world and will give you the enjoyment of our Rapid Service, Copetitive fees and a high client satisfaction rates.</p>
      
          <div class="py-10">
          <p class="font-semibold py-2">ADDRESS</p>
          <p>Address Embassy House unit 4 Harrambee Ave,
          PO BOX 74165 Nairobi Kenya.</p>
          <p class="font-semibold py-2">PHONE</p>
          <p>+245720829302</p>
          <p class="font-semibold py-2">EMAIL</p>
          <p>dytronelimited@outlook.com</p>
          </div>
     
  </div>
  <div class="flex justify-center">
        <h2 class="text-3xl text-zinc-600 font-bold w-full mb-4 md:mb-0 lg:w-6/12">NEED A QUOTE ? CALL US NOW..</h2>
        <a class="inline-flex text-2xl font-normal text-gable-green whitespace-nowrap items-center hover:text-blurple" href="#">+245720829302</a>
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
  email: '',
  password: '',
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
