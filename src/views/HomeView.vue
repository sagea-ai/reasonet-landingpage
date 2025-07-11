<template>
  <section class="relative w-full min-h-screen bg-gradient-to-br from-[#002C58] via-[#97b0f0] to-[#80A1F8] overflow-hidden">
    <!-- Background elements for visual interest -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="blob blob-1"></div>
      <div class="blob blob-2"></div>
      <div class="blob blob-3"></div>
    </div>
    
    <div class="max-w-[1200px] mx-auto px-6 pt-32 md:pt-29 relative z-10">
      <!-- Beta announcement with improved styling -->
      <router-link
        to="/"
        class="inline-block text-[15px] max-sm:items-center text-gray-800 rounded-full hover:scale-105 transition-all duration-300 bg-white/90 backdrop-blur-sm p-1 shadow-lg animate-element"
      >
        <!-- Mobile view -->
        <span class="inline md:hidden font-medium p-2 items-center">
          Introducing Reasonet <span class="ml-1">→</span>
        </span>
        <!-- Desktop view -->
        <span class="hidden md:inline p-2 px-4">
          Reasonet is now live –
          <span class="font-semibold text-black">Try the Strategic Reasoning Engine <span class="ml-1">→</span></span>
        </span>
      </router-link>

      <!-- Main content section -->
      <div class="flex flex-col lg:flex-row justify-between">
        <div class="lg:max-w-[60%]">
          <!-- Main heading with animation -->
          <h1 class="text-[60px] md:text-[72px] font-bold leading-[0.95] tracking-[-0.02em] mt-8 max-w-[900px] text-white heading-text">
            Strategic Reasoning,<br>
            <span class="text-[#000014]">for Founders & Policymakers.</span>
          </h1>

          <!-- Description with improved styling -->
          <p class="mt-8 text-[20px] md:text-[22px] leading-[1.6] text-[#000014] max-w-[600px] description-text">
            Reasonet stress-tests your startup ideas, simulates investor reactions, and uncovers blind spots—so you can build with confidence.
          </p>

          <!-- CTA Buttons with animation -->
          <div class="flex flex-col sm:flex-row gap-4 mt-8 cta-buttons">
            <router-link to="/">
              <button class="w-full sm:w-auto px-8 py-4 bg-[#000014] text-[#FDFDFD] text-[15px] font-semibold rounded-full hover:scale-105 transition-all shadow-lg hover:shadow-xl">
                Try Reasonet
              </button>
            </router-link>
            <a href="#learn-more" class="w-full sm:w-auto px-8 py-4 bg-transparent border-2 border-white text-white text-[15px] font-medium rounded-full hover:bg-black/10 transition-all text-center inline-block">
              Learn more
            </a>
          </div>
                  </div>

        <!-- Dashboard Preview with original styling and animation -->
        <div class="relative mt-8 w-full lg:w-[65%] dashboard-container">
          <div class="transform -rotate-[8deg] translate-y-20 relative max-w-[140%] mx-auto">
            <!-- Gradient overlay -->
            <div class="absolute inset-0 bg-gradient-to-b from-transparent via-transparent to-[#80A1F8] opacity-90 rounded-2xl pointer-events-none z-10" />
            <!-- Dashboard image container -->
            <div class="rounded-2xl shadow-[0_20px_80px_-10px_rgba(0,0,0,0.3)] overflow-hidden hover:shadow-[0_25px_100px_-5px_rgba(0,0,0,0.4)] transition-all duration-700">
              <img
                src="@/assets/dashboard.png"
                alt="Dashboard preview"
                class="w-full rounded-xl bottom-0 dashboard-image"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Keeping all existing components -->
  <div id="learn-more">
    <KeyPoint/>
    <FAQ/>
    <GetStarted/>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import { animate } from 'motion'; // Keeping the Motion library as in original
import FAQ from '@/components/FAQ.vue';
import GetStarted from '@/components/GetStarted.vue';
import KeyPoint from '@/components/KeyPoint.vue';

onMounted(() => {
  // Keeping all original animations exactly as they were
  
  // Animate heading and description text
  animate('.heading-text', 
    { y: [50, 0], opacity: [0, 1] }, 
    { duration: 1.2, easing: [0.33, 1, 0.68, 1] } // power3.out equivalent
  );
  
  animate('.description-text', 
    { y: [30, 0], opacity: [0, 1] }, 
    { duration: 1.2, easing: [0.33, 1, 0.68, 1], delay: 0.3 }
  );
  
  // Animate the CTA buttons
  animate('.cta-buttons', 
    { y: [30, 0], opacity: [0, 1] }, 
    { duration: 1, easing: [0.33, 1, 0.68, 1], delay: 0.6 }
  );
  
  // Animate the beta announcement
  animate('.animate-element', 
    { y: [-20, 0], opacity: [0, 1] }, 
    { duration: 1, easing: [0.175, 0.885, 0.32, 1.275] } // back.out equivalent
  );
  
  // Animate the dashboard image with a reveal effect
  animate('.dashboard-container', 
    { y: [100, 0], opacity: [0, 1] }, 
    { duration: 1, easing: [0.36, 0, 0.66, 1], delay: 0.8 } // power4.out equivalent
  );
  
  // Create a subtle floating animation for the dashboard
  animate('.dashboard-container', 
    { y: [-15, 0, -15] }, 
    { duration: 3, repeat: Infinity, easing: 'ease-in-out' }
  );
});
</script>

<style scoped>
.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
}

.blob-1 {
  width: 600px;
  height: 600px;
  background: rgba(128, 161, 248, 0.5); /* Light Blue - #80A1F8 */
  top: -100px;
  right: -200px;
}

.blob-2 {
  width: 500px;
  height: 500px;
  background: rgba(0, 44, 88, 0.4); /* HSBA Blue - #002C58 */
  bottom: -100px;
  left: -200px;
}

.blob-3 {
  width: 300px;
  height: 300px;
  background: rgba(0, 67, 241, 0.3); /* Blue - #0043F1 */
  top: 30%;
  left: 30%;
}

/* Add a subtle pulse animation to the CTA button */
@keyframes subtle-pulse {
  0% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.7); }
  70% { box-shadow: 0 0 0 10px rgba(255, 255, 255, 0); }
  100% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0); }
}
</style>