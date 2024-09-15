<template>
    <section class="py-16 bg-gray-100">
      <div class="container mx-auto">
        <h3 class="text-2xl text-custom-blue text-left pb-3">Prezentacja firmy</h3>
        <h2 class="text-5xl font-semibold text-left text-custom-grey uppercase font-bebas">Zobacz naszą galerię zdjęć</h2>

        <div class="mt-8 flex justify-left space-x-8">
          <button 
            :class="['text-lg font-semibold', activeTab === 'personal' ? 'text-custom-blue underline' : 'text-gray-400 hover:text-gray-600']"
            @click="activeTab = 'personal'"
          >
            Samochody osobowe
          </button>
          <button 
            :class="['text-lg font-semibold', activeTab === 'cargo' ? 'text-custom-blue underline' : 'text-gray-400 hover:text-gray-600']"
            @click="activeTab = 'cargo'"
          >
            Samochody dostawcze
          </button>
        </div>

        <div class="mt-20 mb-24">
          <swiper :slides-per-view="1" :breakpoints="{
            640: { slidesPerView: 1 },
            768: { slidesPerView: 2 },
            1024: { slidesPerView: 2 }
          }" :pagination="{clickable: true}" class="mySwiper ">
            <swiper-slide v-for="(image, index) in displayedImages" :key="index">
              <img :src="image.src" :alt="image.alt" class="w-75% h-auto object-cover">
            </swiper-slide>
          </swiper>
        </div>
      </div>
    </section>
</template>

  
<script>
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/swiper-bundle.css';
  
  export default {
    components: {
      Swiper,
      SwiperSlide
    },
    data() {
      return {
        activeTab: 'personal',
        personalCars: [
          { src: new URL('../assets/GalleryCar2.png', import.meta.url).href, alt: 'Car 1' },
          { src: new URL('../assets/GalleryCar1.png', import.meta.url).href, alt: 'Car 2' },
          { src: new URL('../assets/GalleryCar3.png', import.meta.url).href, alt: 'Car 3' }
        ],
        cargoCars: [
           
        ]
      };
    },
    computed: {
      displayedImages() {
        return this.activeTab === 'personal' ? this.personalCars : this.cargoCars;
      }
    },
  };
</script>