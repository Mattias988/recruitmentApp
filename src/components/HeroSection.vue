<template>
  <section class="h-screen flex items-center justify-center bg-gray-100 relative">
    <img src="../assets/HeroSectionCars.png" alt="Cars" class="absolute right-0 bottom-0 sm:w-6/7 md:w-3/4 lg:w-3/4 h-auto object-cover opacity-100">
    <div class="container relative z-10">
      <h1 class="text-4xl md:text-5xl lg:text-7xl font-semibold text-custom-grey uppercase font-bebas">Sprzedajemy Samochody <br> z Europy</h1>
      <p class="mt-8 md:mt-12 text-base md:text-lg text-gray-600">Kup komfortowy pojazd, aby każda podróż <br>była wyjątkowym przeżyciem.</p>
      <div class="mt-8 md:mt-12 flex flex-col md:flex-row space-y-4 md:space-y-0 md:space-x-4">
        <Button text="Zobacz zdjęcia" class="bg-custom-blue hover:bg-transparent hover:text-custom-blue hover:border hover:border-custom-blue text-white px-6 py-3 rounded-md" />
        <Button text="Zadzwoń do nas" class="bg-transparent text-custom-blue border border-custom-blue hover:bg-custom-blue hover:text-white px-6 py-3 rounded-md" />
      </div>
    </div>
  </section>
</template>

 
<script>
import Button from './Button.vue';

export default {
  name: 'HeroSection',
  components: {
    Button
  }
}
</script>
 