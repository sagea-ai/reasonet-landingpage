<template>
    <div class=" bg-white">
      <div class="px-8 py-12 md:m-12">
        <div class="flex items-center gap-2 mb-4">
        </div>
  
        <!-- Card Section -->
        <div class="rounded-[2rem] bg-cover bg-center p-16 back bg-[url('@/assets/circles-blur.jpg')]">
          <div class="max-w-2xl">
            <p class="text-gray-600 mb-4 text-lg">Get started</p>
            
            <h2 class="text-[2rem] leading-[1.2] font-bold text-black mb-4">
              Take your startup to the next level with Reasonet today.
            </h2>
            
            <p class="text-gray-600 mb-8 text-md">
              Reasonet is your strategic reasoning engine—stress-test ideas, simulate investors, and build with confidence.
            </p>
            
            <router-link to="/">
            <button class="bg-black text-white px-6 py-3 rounded-full text-sm font-medium hover:bg-black/90 transition-colors border-gray-400">
              Try Reasonet
            </button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  // Component uses only Tailwind for styling
  </script>