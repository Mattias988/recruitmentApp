<template>
    <div>
      <Navbar />
      <HeroSection />
      <Gallery />
      <Footer />
    </div>
  </template>
  
  <script>
  import Navbar from '../components/Navbar.vue';
  import HeroSection from '../components/HeroSection.vue';
  import Gallery from '../components/Gallery.vue';
  import Footer from '../components/Footer.vue';
  
  export default {
    name: 'Home',
    components: {
      Navbar,
      HeroSection,
      Gallery,
      Footer
    }
  }
  </script>
  