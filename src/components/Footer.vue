<template>
    <footer class="bg-custom-grey text-white py-8">
      <div class="container mx-auto grid grid-cols-1 lg:grid-cols-2 gap-8">
        <div>
          <h3 class="text-lg font-semibold mb-4 ">ID NOSTRUD ENIM ESSE CONSECTETUR IN EU MOLLIT FUGIAT AUTE. VELIT NULLA COMMODO.</h3>
          <p class="text-sm ">
            Mauris varius ipsum mauris, rutrum lobortis magna efficitur a. Donec egestas, nisl vehicula feugiat ornare, diam turpis
            efficitur mi, ac venenatis eros ipsum ac arcu. Vestibulum et ...
          </p>
          <p v-if="isExpanded[0]" class="text-sm mt-2 ">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua.
          </p>
          <button @click="toggleExpand(0)" class="mt-4 text-sm underline flex items-center">
            {{ isExpanded[0] ? 'Zwiń' : 'Rozwiń' }}
            <img :src="arrowIcon" :class="isExpanded[0] ? 'rotate-180' : 'rotate-0'" alt="Arrow" class="w-4 h-4 ml-2 transition-transform duration-300">
          </button>
        </div>

        <div>
          <h3 class="text-lg font-semibold mb-4 ">ID NOSTRUD ENIM ESSE CONSECTETUR IN EU MOLLIT FUGIAT AUTE. VELIT NULLA COMMODO.</h3>
          <p class="text-sm ">
            Mauris varius ipsum mauris, rutrum lobortis magna efficitur a. Donec egestas, nisl vehicula feugiat ornare, diam turpis
            efficitur mi, ac venenatis eros ipsum ac arcu. Vestibulum et ...
          </p>
          <p v-if="isExpanded[1]" class="text-sm mt-2">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua.
          </p>
          <button @click="toggleExpand(1)" class="mt-4 text-sm underline flex items-center">
            {{ isExpanded[1] ? 'Zwiń' : 'Rozwiń' }}
            <img :src="arrowIcon" :class="isExpanded[1] ? 'rotate-180' : 'rotate-0'" alt="Arrow" class="w-4 h-4 ml-2 transition-transform duration-300">
          </button>
        </div>
      </div>

      <div class="w-full">
        <hr class="border-t border-white my-8 mx-auto" />
      </div>

      <div class="container mx-auto flex flex-col lg:flex-row justify-between items-center space-y-4 lg:space-y-0">
        <div class="font-semibold">CarsSpot</div>
        <a href="#" class="text-sm underline">Polityka prywatności</a>
      </div>
    </footer>
</template>

  
  <script>
  import arrowIcon from '../assets/arrow.svg';
  
  export default {
    data() {
      return {
        isExpanded: [false, false],
        arrowIcon, 
      };
    },
    methods: {
      toggleExpand(index) {
        this.isExpanded[index] = !this.isExpanded[index];
      }
    }
  };
  </script>
  
  <style scoped>
  .rotate-0 {
    transform: rotate(0deg);
  }
  .rotate-180 {
    transform: rotate(180deg);
  }
  </style>
  