<template>
    <nav :class="['fixed w-full top-0 left-0 z-50 transition-all duration-300', isScrolled ? 'bg-white shadow-lg' : 'bg-transparent']">
      <div class="container mx-auto flex justify-between items-center py-4">
        <div class="flex items-center space-x-2">
          <img src="../assets/logo.svg" alt="Logo" class="w-8 h-8">
          <span class="text-2xl font-bold font-poppins">
            <span class="text-custom-blue">Cars</span><span class="text-black">Spot</span>
          </span>
        </div>

        <!-- Przycisk menu hamburger na mobilnych urządzeniach -->
        <div class="lg:hidden">
          <button @click="isMobileMenuOpen = !isMobileMenuOpen" class="focus:outline-none">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>

        <!-- Menu na urządzeniach powyżej lg -->
        <ul class="hidden lg:flex space-x-8">
          <li><a href="#gallery" class="hover:text-gray-400 text-black">Galeria zdjęć</a></li>
          <li><a href="#faq" class="hover:text-gray-400 text-black">FaQ</a></li>
        </ul>

        <!-- Przycisk na desktopie -->
        <div class="hidden lg:block">
          <Button text="Zadzwoń do nas" class="bg-custom-blue hover:bg-transparent hover:text-custom-blue hover:border hover:border-custom-blue text-white px-4 py-2 rounded-lg" />
        </div>
      </div>

      <!-- Mobilne menu -->
      <div v-if="isMobileMenuOpen" class="lg:hidden">
        <ul class="space-y-4 px-8 py-4 bg-white shadow-lg">
          <li><a href="#gallery" class="hover:text-gray-400 text-black">Galeria zdjęć</a></li>
          <li><a href="#faq" class="hover:text-gray-400 text-black">FAQ</a></li>
          <li><Button text="Zadzwoń do nas" class="bg-custom-blue text-white w-full py-2 rounded-md hover:bg-transparent hover:text-custom-blue hover:border hover:border-custom-blue" /></li>
        </ul>
      </div>
    </nav>
  </template>

<script>
import Button from './Button.vue';

export default {
  name: 'Navbar',
  components: {
    Button
  },
  data() {
    return {
      isScrolled: false,
      isMobileMenuOpen: false, // Nowa zmienna dla mobilnego menu
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50;
    },
  },
};
</script>
