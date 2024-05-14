import InstagramPosts from 'components/InstagramPosts.vue';

<template>
  <NuxtLayout name="landing">
    <div>
      <!--<TemplrJSCarousel/>-->
      
      <TemplrJSHero api_end_point="/configs/hero" />

      <TemplrJSDocCard :data="data" class="m-2 pb-2 py-10" />
      <BlogRecent />
      <TemplrJSMarquee api_end_point="/configs/tech-stack" />
     <!--<InstagramPosts/>-->
    </div>
  </NuxtLayout>
</template>
<script setup>
const page_meta = [];

const data = [
  {
    heading: "GLOBAL EXPERTISE, LOCAL SOLUTIONS",
    paragraph:
      "Dytrone's unparalleled global network and experience uniquely position the company to provide localized solutions with a global perspective. We understand the intricacies of international markets, offering clients the advantage of tailored strategies suited to diverse business environments.",
    textColor: "text-violet-100",
    buttonText: "Explore My Work",
    bgFrom: "from-purple-500",
    buttonColor: "bg-indigo-800",
    bgTo: "to-indigo-500",
    link: "/projects",
  },
  {
    heading: "END-TO-END SERVICE SPECTRUM",
    paragraph:
      "From software development to lean manufacturing and client acquisition, Dytrone offers a comprehensive suite of services, ensuring that clients can address multiple facets of their business needs under one roof. This integrated approach streamlines processes, maximizes efficiency, and minimizes the complexities of dealing with multiple service providers.",
    textColor: "text-rose-100",
    buttonText: "Access Resources",
    bgFrom: "from-pink-500",
    buttonColor: "bg-rose-900",
    bgTo: "to-rose-500",
    link: "/docs/getting-started",
  },
  {
    heading: "STRATEGIC PARTNERSHIPS IN EMERGING MARKETS",
    paragraph:
      "Dytrone's focus on the rapidly growing economies of China and India sets it apart. The company facilitates strategic partnerships with reputable firms in these regions, enabling clients to tap into lucrative markets and expand their global footprint.",
    textColor: "text-amber-100",
    buttonText: "View Documentation",
    bgFrom: "from-yellow-400",
    buttonColor: "bg-orange-600",
    bgTo: "to-orange-500",
    link: "/docs/api",
  },
];

useNuxtApp().$bus.$on("hero_templrjs_click", async (args) => {
  //useRouter().push({ path: '/cms/templrjs'})
  document.location.href = "/cms/templrjs";
});

useNuxtApp().$bus.$on("hero_getstarted_click", async (args) => {
  window.open("https://github.com/senthilsweb/templrjs", "_blank");
});

/*let properties_query = `/configs/properties.json`;
const properties = await useFetch(properties_query, {
  method: 'get',
});
propertiesStore.reloadProperties(properties.data._rawValue);

let countries_query = `/configs/countries.json`;
const countries = await useFetch(countries_query, {
  method: 'get',
});
countryStore.reloadCountry(countries.data._rawValue);

let company_query = `/configs/company.json`;
const company = await useFetch(company_query, {
  method: 'get',
});
companyStore.reloadCompany(company.data._rawValue[0]);


let query_child = `/configs/child_nav.json`;
const child = await useFetch(query_child, {
  method: 'get',
});

let query_parent = `/configs/parent_nav.json`;
const parent = await useFetch(query_parent, {
  method: 'get',
});
navigationsStore.reloadNavigations(useUnion(child.data._rawValue, parent.data._rawValue));
*/
</script>
