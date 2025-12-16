<template>
  <header class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-green-100/50 shadow-sm transition-all duration-300" role="banner">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <div class="flex items-center animate-fade-in-left">
        <img 
          src="/images/Simka Buah Medan_UP.jpg" 
          alt="Logo SIMKA Buah Medan" 
          class="h-10 w-10 rounded-full object-cover mr-2 sm:mr-3 border-2 border-green-200 shadow-sm"
        />
        <h1 class="text-lg sm:text-xl font-bold text-green-700 tracking-tight">SIMKA Buah Medan</h1>
      </div>

      <!-- Mobile menu button -->
      <button
        class="md:hidden text-gray-600 focus:outline-none animate-fade-in-right p-2 hover:bg-green-50 rounded-full transition-colors"
        @click="toggleMobileMenu"
        :aria-expanded="mobileMenuOpen"
        aria-controls="mobile-menu"
        :aria-label="mobileMenuOpen ? 'Tutup menu navigasi' : 'Buka menu navigasi'"
      >
        <svg
          v-if="!mobileMenuOpen"
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          ></path>
        </svg>
        <svg
          v-else
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          ></path>
        </svg>
      </button>

      <!-- Desktop navigation -->
      <nav class="hidden md:flex items-center space-x-1 animate-fade-in-right" role="navigation" aria-label="Navigasi utama">
        <a href="#home" class="px-4 py-2 text-gray-600 hover:text-green-700 hover:bg-green-50 rounded-full transition-all duration-300 font-medium text-sm sm:text-base">Beranda</a>
        <a href="#features" class="px-4 py-2 text-gray-600 hover:text-green-700 hover:bg-green-50 rounded-full transition-all duration-300 font-medium text-sm sm:text-base">Keunggulan</a>
        <a href="#gallery" class="px-4 py-2 text-gray-600 hover:text-green-700 hover:bg-green-50 rounded-full transition-all duration-300 font-medium text-sm sm:text-base">Galeri</a>
        <a href="#testimoni" class="px-4 py-2 text-gray-600 hover:text-green-700 hover:bg-green-50 rounded-full transition-all duration-300 font-medium text-sm sm:text-base">Testimoni</a>
        <a href="#cta" class="px-4 py-2 text-green-700 bg-green-50 hover:bg-green-100 hover:text-green-800 rounded-full transition-all duration-300 font-bold text-sm sm:text-base shadow-sm hover:shadow">Hubungi</a>
      </nav>
    </div>

    <!-- Mobile navigation -->
    <div
      v-if="mobileMenuOpen"
      id="mobile-menu"
      class="md:hidden bg-white py-4 px-4 border-t animate-slide-in-down"
      role="navigation"
      aria-label="Menu navigasi mobile"
    >
      <div class="flex flex-col space-y-3">
        <a href="#home" class="text-gray-700 hover:text-green-600 font-medium py-2 text-base">Beranda</a>
        <a href="#features" class="text-gray-700 hover:text-green-600 font-medium py-2 text-base">Keunggulan</a>
        <a href="#gallery" class="text-gray-700 hover:text-green-600 font-medium py-2 text-base">Galeri</a>
        <a href="#testimoni" class="text-gray-700 hover:text-green-600 font-medium py-2 text-base">Testimoni</a>
        <a href="#cta" class="text-gray-700 hover:text-green-600 font-medium py-2 text-base">Hubungi</a>
      </div>
    </div>
  </header>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Header',
  setup() {
    const mobileMenuOpen = ref(false)

    const toggleMobileMenu = () => {
      mobileMenuOpen.value = !mobileMenuOpen.value
    }

    return {
      mobileMenuOpen,
      toggleMobileMenu
    }
  }
}
</script>
