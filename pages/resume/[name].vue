<template>
  <NuxtLayout name="landing">
     <BlogRecent />
     <TemplrJSMarquee api_end_point="/configs/tech-stack" />
  </NuxtLayout>
</template>
<script setup>


import { useCloudinaryConfig, computeCloudinaryURL } from '~/utils/functions';


import html2canvas from 'html2canvas';
import { jsPDF } from 'jspdf';
import _ from 'lodash';
import dayjs from 'dayjs';

definePageMeta({});

const { path } = useRoute();
const showHeader = ref(true);
const runtimeConfig = useRuntimeConfig();

//const params = new URLSearchParams(window.location.search);
//showHeader.value = params.get('print') === 'true' ? false : true;

//const name = params.get('name'); // returns 'John'
//console.log('name=', name);
//https://res.cloudinary.com/nathansweb/image/upload/v1713630133/senthilsweb.com/senthilsweb-blog-card-indigo_mn0ikl.png
const data = await $fetch(`${useRuntimeConfig().public.TEMPLRJS_CONFIG_ROOT_PATH}/${useRoute().params.name}.json`, {
  method: 'get',
});
const cloudinaryURL = ref('');
const resume_title = ref(`Resume of ${data.basics.name}`)
const config = useCloudinaryConfig(resume_title.value, useRuntimeConfig().public.CLOUDINARY_BASE_URL, 'v1713630133/senthilsweb.com/senthilsweb-blog-card-indigo_mn0ikl.png')
cloudinaryURL.value = computeCloudinaryURL(config.value);
  //console.log(`cloudinaryURL = ${cloudinaryURL.value}`)

const generatePDF = async () => {
  const resumeElement = document.querySelector('#resume');

  // Generate canvas from the content inside the 'resume' div with adjusted scale
  const canvas = await html2canvas(resumeElement, {
    scale: 2, // Adjust this value for optimal balance between size and quality
    useCORS: true,
    allowTaint: true,
    windowWidth: resumeElement.scrollWidth,
    windowHeight: resumeElement.scrollHeight,
  });

  // Convert canvas to a compressed JPEG image
  const imgData = canvas.toDataURL('image/jpeg', 1); // Adjust the quality value between 0 (worst) to 1 (best)

  const pdf = new jsPDF('p', 'mm', 'a4', { compression: true });

  // Margins for the PDF (in mm)
  const topMargin = 10;
  const leftMargin = 2;
  const rightMargin = 2;
  const bottomMargin = 10;

  const pdfWidth = pdf.internal.pageSize.getWidth() - leftMargin - rightMargin;
  const imgProps = pdf.getImageProperties(imgData);
  const pdfHeight = (imgProps.height * pdfWidth) / imgProps.width;

  // Split the image into multiple parts to fit into pages
  let heightLeft = pdfHeight;
  let position = 0; // Start from the top of the image

  let pageNumber = 1;

  while (heightLeft >= 0) {
    // Add the image slice for the current page
    pdf.addImage(imgData, 'JPEG', leftMargin, topMargin - position, pdfWidth, pdfHeight);

    // Add page number at the bottom right corner
    pdf.setFontSize(11);
    pdf.text(`Page ${pageNumber}`, pdf.internal.pageSize.getWidth() - rightMargin - 10, pdf.internal.pageSize.getHeight() - bottomMargin, { align: 'right' });

    heightLeft -= pdf.internal.pageSize.getHeight() - topMargin - bottomMargin;
    position += pdf.internal.pageSize.getHeight() - topMargin - bottomMargin;

    // If there's still content left, add a new page
    if (heightLeft >= 0) {
      pdf.addPage();
      pageNumber++;
    }
  }

  pdf.save(`resume_of_${useRoute().params.name}_${dayjs().unix()}.pdf`);
};

useHead({
  title: resume_title.value, // Combining blog title with website brand
  meta: [
    { name: 'description', content: `${data.basics.summary}` },
    { property: 'og:description', content: `${data.basics.summary}` },
    { property: 'og:title', content: resume_title.value },
    { property: 'og:image', content: cloudinaryURL.value },
    { name: 'twitter:title', content: resume_title.value },
    { name: 'twitter:image', content: cloudinaryURL.value },
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:description', content: resume_title.value },
  ],
});
</script>
