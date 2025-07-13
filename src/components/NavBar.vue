<template>
  <div class="fixed top-0 left-0 right-0 z-50 px-4 py-4">
    <nav class="max-w-4xl mx-auto bg-neutral-100/60 backdrop-blur-sm rounded-3xl drop-shadow-sm">
      <div class="px-6 h-[60px] flex items-center">
        <!-- Logo Section (Left-aligned) -->
        <div class="flex-shrink-0 flex items-center w-1/4">
          <router-link to="/" class="flex items-center">
            <span class="tracking-tight"><img src="@/assets/logo.png" class="h-10 w-10" alt="Reasonet logo"></span>
            <span class="text-[18px] font-bold tracking-tight text-black ml-2">Reasonet</span>
          </router-link>
        </div>
  
        <!-- Navigation Links (Center-aligned) -->
        <div class="hidden md:flex flex-grow justify-center items-center">
          <!-- No navigation items for single landing page -->
        </div>
  
        <!-- Auth Buttons (Right-aligned) -->
        <div class="hidden md:flex flex-shrink-0 items-center justify-end space-x-4 w-1/4">
          <router-link 
            to="https://app-reasonet.sagea.space"
            class="text-[14px] font-medium bg-black text-white px-4 py-2 rounded-full hover:opacity-90 transition-opacity"
          >
            Login
          </router-link>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden ml-auto">
          <button 
            @click="isMobileMenuOpen = !isMobileMenuOpen"
            class="p-2"
          >
            <svg
              class="w-6 h-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path 
                v-if="!isMobileMenuOpen"
                stroke-linecap="round" 
                stroke-linejoin="round" 
                stroke-width="2" 
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    
      <!-- Mobile Menu -->
      <div 
        v-show="isMobileMenuOpen"
        class="md:hidden border-t border-gray-300"
      >
        <div class="px-4 py-2 space-y-1">
          <router-link
            to="/login"
            class="block mt-4 text-center text-[15px] font-medium bg-black text-white px-5 py-2.5 rounded-full"
            @click="isMobileMenuOpen = false"
          >
            Login
          </router-link>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navigationItems = [
  { name: 'Pricing', href: '/pricing' },
  { name: 'Story', href: '/story' },
  { name: 'Learn', href: '/learn' },
]
</script>
