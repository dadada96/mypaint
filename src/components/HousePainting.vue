<template>
  <section>
    <div class="relative">
      <img class="object-cover h-[calc(100vh-380px)] sm:h-[calc(100vh-160px)] w-full opacity-15"
        src="@/assets/images/house.webp" alt="house-hero-image">
      <div class="text-center absolute top-[50%] left-[50%] -translate-[50%] w-full sm:w-[550px] px-4">
        <section>
          <h1 class="text-[40px]/[40px] sm:text-[70px]/[80px] font-bold">Professional House Painting Service In Kl &
            Selangor</h1>
        </section>
        <section class="mt-8">
          <h3 class="text-[20px] font-[300]">Hire Experienced <span class="font-[500]">House Painters</span></h3>
          <h3 class="text-[20px] font-[300]">No.1 Trusted Wall & Ceiling <span class="font-[500]">House Painting</span>
            Specialist</h3>
        </section>
        <section class="mt-8 flex flex-col sm:flex-row w-full items-center sm:justify-between gap-4 sm:gap-10">
          <button
            class="cursor-pointer rounded-lg max-w-[250px] sm:max-w-none bg-red-500 text-white hover:bg-orange-500 text-[22px] p-4 w-full transition-all">Get
            Free Quote</button>
          <button @click="scrollToSection()"
            class="cursor-pointer rounded-lg max-w-[250px] sm:max-w-none outline outline-red-500 text-red-500 hover:bg-red-500 hover:text-white text-[22px] p-4 w-full transition-all">See
            Services</button>
        </section>
      </div>
    </div>
  </section>
  <section ref="myServiceElement" class="text-center px-6 py-17">
    <h2 class="text-[37px] font-bold tracking-wide">Interior & Exterior Painting Solutions</h2>
    <p class="text-[19px] my-4">With a strong reputation for quality and customer satisfaction, we take pride in
      delivering exceptional results.</p>
    <nav>
      <ul class="flex justify-center">
        <li class="grow w-full">
          <button class="h-[44px] w-full bg-gray-200 font-bold text-gray-700 cursor-pointer transition-all duration-200"
            :class="{ 'bg-red-500 text-white': activeTabIndex === 0 }" @click="tabClicked(0)">
            Interior
          </button>
        </li>
        <li class="grow w-full">
          <button class="h-[44px] w-full bg-gray-200 font-bold text-gray-700 cursor-pointer transition-all duration-200"
            :class="{ 'bg-red-500 text-white': activeTabIndex === 1 }" @click="tabClicked(1)">
            Exterior
          </button>
        </li>
        <li class="grow w-full">
          <button class="h-[44px] w-full bg-gray-200 font-bold text-gray-700 cursor-pointer transition-all duration-200"
            :class="{ 'bg-red-500 text-white': activeTabIndex === 2 }" @click="tabClicked(2)">
            Specialized
          </button>
        </li>
      </ul>
    </nav>
    <ul v-show="activeTabIndex === 0" class="grid grid-cols-1 sm:grid-cols-3 gap-8 px-4 py-8 border border-gray-200">
      <template v-for="item in interiorData" :key="item.title">
        <ServiceCard :image="item.image" :title="item.title" :sub-title="item.subTitle" />
      </template>
    </ul>
    <ul v-show="activeTabIndex === 1" class="grid grid-cols-1 sm:grid-cols-3 gap-8 px-4 py-8 border border-gray-200">
      <template v-for="item in exteriorData" :key="item.title">
        <ServiceCard :image="item.image" :title="item.title" :sub-title="item.subTitle" />
      </template>
    </ul>
    <ul v-show="activeTabIndex === 2" class="grid grid-cols-1 sm:grid-cols-3 gap-8 px-4 py-8 border border-gray-200">
      <template v-for="item in specializedData" :key="item.title">
        <ServiceCard :image="item.image" :title="item.title" :sub-title="item.subTitle" />
      </template>
    </ul>
  </section>
  <section class="text-center mb-30">
    <h1 class="text-[37px] font-bold">Why Choose Us as Your Trusted Painting Contractor</h1>
    <div class="flex justify-self-center h-[6px] bg-red-500 w-[48%] my-6"></div>
    <ChooseUs />
  </section>
  <section class="text-center px-12">
    <h1 class="text-[37px]/[50px] font-bold mb-6">Expertly Qualified<br>Our Qualifications Set Us Apart</h1>
    <p class="text-[20px]">Settle for nothing but the best. We brings a wealth of qualifications and
      certifications in the painting
      industry, guaranteeing exceptional solutions for your space.</p>
    <div class="flex flex-wrap justify-center mt-4 gap-4">
      <img src="@/assets/logos/dulux.png" alt="dulux-logo-icon" class="w-[200px] h-auto object-contain">
      <img src="@/assets/logos/nippon.png" alt="nippon-logo-icon" class="w-[200px] h-auto object-contain">
      <img src="@/assets/logos/jotun.png" alt="jotun-logo-icon" class="w-[200px] h-auto object-contain">
    </div>
  </section>
  <section class="text-center px-12 my-15 py-15 bg-gray-50">
    <h1 class="text-[37px]/[50px] font-bold mb-6">Painting Made Easy</h1>
    <p class="text-[20px] mb-6">Our 4-Step Process for Stunning Results.</p>
    <StepCard />
  </section>
  <section class="text-center px-12 my-15 py-15">
    <h1 class="text-[32px]/[50px] font-bold mb-6">Trusted By Over 500+ Clients<br>Since 2014</h1>
    <div class="flex flex-col sm:flex-row justify-center gap-8 sm:gap-14 my-15">
      <h1 class="mb-6">
        <p class="text-[50px]/[50px] font-bold text-red-500">500 000+</p>
        <p class="text-[24px] text-gray-500 mt-3">Sqft Painted<br>With Excellence</p>
      </h1>
      <h1 class="mb-6">
        <p class="text-[50px]/[50px] font-bold text-red-500">10+</p>
        <p class="text-[24px] text-gray-500 mt-3">Years Of<br>Combined Experience</p>
      </h1>
    </div>
  </section>
  <section class="text-center px-12 my-15 py-15 bg-gray-50">
    <h1 class="text-[37px]/[50px] font-bold mb-6">Hear It From Our Happy Customers</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-14 my-15">
      <div class="bg-white rounded-lg p-10 text-start">
        <div class="flex mb-6">
          <template v-for="star in 5" :key="star">
            <img src="@/assets/icons/star-solid-full.svg" alt="star-icon"
              class="w-7 h-7 [filter:invert(85%)_sepia(50%)_saturate(2000%)_hue-rotate(350deg)_brightness(105%)_contrast(100%)]">
          </template>
        </div>
        <p class="text-[18px]/[30px] italic">"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
          tempor
          incididunt
          ut labore et dolore
          magna aliqua."</p>
        <div class="mt-6 ml-4">
          <p class="text-[18px] font-500">Abcdeff</p>
          <p class="text-[18px] font-300 text-gray-500">Shah Alam, Selangor</p>
        </div>
      </div>

      <div class="bg-white rounded-lg p-10 text-start">
        <div class="flex mb-6">
          <template v-for="star in 5" :key="star">
            <img src="@/assets/icons/star-solid-full.svg" alt="star-icon"
              class="w-7 h-7 [filter:invert(85%)_sepia(50%)_saturate(2000%)_hue-rotate(350deg)_brightness(105%)_contrast(100%)]">
          </template>
        </div>
        <p class="text-[18px]/[30px] italic">"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
          tempor
          incididunt
          ut labore et dolore
          magna aliqua."</p>
        <div class="mt-6 ml-4">
          <p class="text-[18px] font-500">Abcdeff</p>
          <p class="text-[18px] font-300 text-gray-500">Shah Alam, Selangor</p>
        </div>
      </div>

      <div class="bg-white rounded-lg p-10 text-start">
        <div class="flex mb-6">
          <template v-for="star in 5" :key="star">
            <img src="@/assets/icons/star-solid-full.svg" alt="star-icon"
              class="w-7 h-7 [filter:invert(85%)_sepia(50%)_saturate(2000%)_hue-rotate(350deg)_brightness(105%)_contrast(100%)]">
          </template>
        </div>
        <p class="text-[18px]/[30px] italic">"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
          tempor
          incididunt
          ut labore et dolore
          magna aliqua."</p>
        <div class="mt-6 ml-4">
          <p class="text-[18px] font-500">Abcdeff</p>
          <p class="text-[18px] font-300 text-gray-500">Shah Alam, Selangor</p>
        </div>
      </div>
    </div>
  </section>
  <section class="text-center px-6 sm:px-12 my-15 py-15">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-3">
      <template v-for="portfolio in 9" :key="portfolio">
        <img src="@/assets/images/house.webp" alt="portfolio-image" class="rounded-lg">
      </template>
    </div>
  </section>
  <section class="text-center px-12 my-15 py-15 bg-gray-50">
    <h1 class="text-[37px] font-bold capitalize">Get a quote for your house painting project today.</h1>
    <p class="text-[20px] text-gray-600 my-4">Simply click the button, fill out the form, and you’ll be connected with
      our
      project advisor
      via WhatsApp.</p>
    <button
      class="cursor-pointer rounded-lg bg-red-500 text-white hover:bg-orange-500 text-[18px] py-2 px-4 mt-4 transition-all"
      @click="sendWhatsapp()">
      <div class="flex justify-center items-center"><img src="@/assets/icons/whatsapp-brands-solid-full.svg"
          alt="whatsapp-icon" class="invert w-8 h-8">
        Whatsapp
        Now</div>
    </button>
  </section>
  <section class="bg-slate-800">
    <div class="flex flex-col sm:flex-row justify-between py-6 px-18 gap-6 text-white text-center sm:text-start">
      <div>
        <p class="text-[16px]">Company name</p>
        <p class="text-[16px]">Company address 1</p>
        <p class="text-[16px]">Company address 2</p>
      </div>
      <div class="flex items-center justify-center gap-6">
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/facebook-brands-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/instagram-brands-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/tiktok-brands-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/whatsapp-brands-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/mobile-screen-button-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
        <button class="cursor-pointer hover:opacity-60 transition-all">
          <img src="@/assets/icons/envelope-solid-full.svg" alt="social-media" class="w-5 h-5 invert">
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, useTemplateRef } from 'vue';
import ServiceCard from './ServiceCard.vue';
import paintWallImg from '@/assets/images/paint-wall.webp';
import textureWallImg from '@/assets/images/texture-wall.webp';
import removeWallpaperImg from '@/assets/images/remove-wallpaper.webp';
import doorPaintImg from '@/assets/images/door-paint.webp';
import trimPaintImg from '@/assets/images/trim-paint.webp';
import exteriorPaintImg from '@/assets/images/exterior-paint.webp';
import grillPaintImg from '@/assets/images/grill-paint.webp';
import roofPaintImg from '@/assets/images/roof-paint.webp';
import highrisePaintImg from '@/assets/images/highrise-paint.webp';
import muralPaintImg from '@/assets/images/mural-paint.webp';
import cabinetPaintImg from '@/assets/images/cabinet-paint.webp';
import epoxyPaintImg from '@/assets/images/epoxy-paint.webp';
import roadPaintImg from '@/assets/images/road-paint.webp';
import preparePaintImg from '@/assets/images/prepare-paint.webp';
import waterproofPaintImg from '@/assets/images/waterproof-paint.webp';
import ChooseUs from './ChooseUs.vue';
import StepCard from './StepCards.vue';

const myServiceElement = useTemplateRef('myServiceElement')

const activeTabIndex = ref(0)

const interiorData = ref([
  {
    image: paintWallImg,
    title: 'Wall & Ceiling Painting',
    subTitle: 'Brighten up your room, walls and ceiling with top quality Nippon or Jotun paints. Ideal for homes, bedrooms, and renovations.',
  },
  {
    image: textureWallImg,
    title: 'Texture & Decoration Painting',
    subTitle: 'Add unique textures and decorative design like Momento, Limewash, Cement Effect & Geometry. Great for feature walls and modern interiors.'
  },
  {
    image: removeWallpaperImg,
    title: 'Wallpaper Removal',
    subTitle: 'Safely remove old wallpaper without damage and prepare your walls for a fresh new look.',
  },
  {
    image: doorPaintImg,
    title: 'Grill and Door Painting',
    subTitle: 'Protect and refresh doors and grills with durable & anti-rust paint in matte or gloss finish.'
  },
  {
    image: trimPaintImg,
    title: 'Trim and Cornice Painting',
    subTitle: 'Achieve a polished look with precise painting of trims, cornices, and skirting boards.'
  },
])

const exteriorData = ref([
  {
    image: exteriorPaintImg,
    title: 'Wall Painting',
    subTitle: 'Enhance your exterior walls with long-lasting paint that protects against heat, rain, and fading. Ideal for any landed home or outdoor surface.',
  },
  {
    image: grillPaintImg,
    title: 'Gate, Grill & Door Painting',
    subTitle: 'Durable anti-rust painting for gates, grills, and wooden doors. Great for outdoor exposure and a clean, refreshed look.'
  },
  {
    image: roofPaintImg,
    title: 'Roof Painting',
    subTitle: 'Protect and brighten your roof with heat-reflective and weatherproof coatings. Helps extend roof lifespan and improve home insulation.'
  },
  {
    image: highrisePaintImg,
    title: 'Highrise Painting',
    subTitle: 'We paint high-rise buildings with gondola, skylift, and rope access. Durable results for commercial facades, apartments, and towers.'
  },
])

const specializedData = ref([
  {
    image: muralPaintImg,
    title: 'Mural Painting',
    subTitle: 'Create a standout wall with custom murals designed for bold, artistic impact.',
  },
  {
    image: cabinetPaintImg,
    title: 'Cabinet Painting',
    subTitle: 'Revamp your cabinets with precise spray painting techniques for a smooth, flawless finish.'
  },
  {
    image: epoxyPaintImg,
    title: 'Epoxy Painting',
    subTitle: 'Strengthen your floors with durable, high-gloss epoxy coatings that look great and last long.'
  },
  {
    image: roadPaintImg,
    title: 'Road Marking Painting',
    subTitle: 'Precise and durable road markings with high-quality reflective paints, enhancing visibility and safety for roads, parking lots, and industrial areas.'
  },
  {
    image: preparePaintImg,
    title: 'Surface Preparation',
    subTitle: 'Clean, skim, patch, sand, and prime surfaces for optimal paint adhesion and a smooth finish.',
  },
  {
    image: waterproofPaintImg,
    title: 'Waterproofing',
    subTitle: 'Seal roofs, basements, and walls with waterproof coatings to prevent leaks and moisture damage.'
  },
])

const scrollToSection = () => {
  myServiceElement.value?.scrollIntoView({ behavior: 'smooth' })
}

const tabClicked = (tabIndex) => {
  activeTabIndex.value = tabIndex
}

const sendWhatsapp = () => {
  const phone = '601127363634'
  const message = 'Hi there!'
  const url = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`
  window.open(url, '_blank')
}
</script>
