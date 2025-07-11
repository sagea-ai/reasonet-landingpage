<template>
  <div class="relative w-full overflow-hidden py-16 sm:py-20 bg-gradient-to-r from-[#FDFDFD] to-[#F3F3F3]">
    <!-- Title Section -->
    <div class="container mx-auto text-center mb-8 sm:mb-10">
      <h2 class="text-[#002C58] text-lg sm:text-xl font-medium mb-2">Trusted by early-stage founders and innovators</h2>
      <p class="text-[#002C58]/60 text-sm sm:text-base max-w-md mx-auto">
        Join the community using Reasonet to stress-test ideas and simulate investor feedback.
      </p>
    </div>

    <!-- Scrolling Logos (Full Width) -->
    <div class="relative w-full overflow-hidden">
      <!-- Gradient Overlays -->
      <div class="absolute left-0 top-0 w-20 h-full bg-gradient-to-r from-[#F3F3F3] to-transparent z-10"></div>
      <div class="absolute right-0 top-0 w-20 h-full bg-gradient-to-l from-[#F3F3F3] to-transparent z-10"></div>

      <div class="overflow-hidden w-full">
        <div ref="logosContainerRef" class="logos-container flex items-center">
          <a v-for="n in 7" :key="n" href="#" class="mx-6 sm:mx-10 group flex-shrink-0">
            <img
              :src="`/assets/logo.png`"
              :alt="`Company ${n}`"
              class="w-24 sm:w-32 md:w-36 h-auto object-contain invert transition-all duration-300"
              loading="lazy"
            />
          </a>
          <!-- Duplicate logos for seamless scrolling -->
          <a v-for="n in 7" :key="`d${n}`" href="#" class="mx-6 sm:mx-10 group flex-shrink-0">
            <img
              :src="`/assets/logo.png`"
              :alt="`Company ${n}`"
              class="w-24 sm:w-32 md:w-36 h-auto object-contain invert transition-all duration-300"
              loading="lazy"
            />
          </a>
          <a v-for="n in 7" :key="`t${n}`" href="#" class="mx-6 sm:mx-10 group flex-shrink-0">
            <img
              :src="`/assets/logo.png`"
              :alt="`Company ${n}`"
              class="w-24 sm:w-32 md:w-36 h-auto object-contain invert transition-all duration-300"
              loading="lazy"
            />
          </a>
        </div>
      </div>
    </div>
    
    <!-- Social Proof -->
    <div class="container mx-auto mt-16 text-center">
      <div class="inline-flex items-center justify-center px-4 py-2 rounded-full bg-emerald-100 text-emerald-500">
        <span class="font-medium">20+</span>
        <span class="mx-2">•</span>
        <span>People using Reasonet daily</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const logos = ref([
  { id: 1, src: "/assets/invelio.png", backlink: "https://invelio.space", alt: "Invelio" },
  { id: 2, src: "/assets/qubeguard.png", backlink: "https://qubeguard.com", alt: "Qubeguard" },
  { id: 3, src: "/assets/offtop.png", backlink: "https://offtop.co", alt: "Offtop" },
  { id: 4, src: "/assets/paytree.png", backlink: "https://paytree.tech", alt: "Paytree" },
  { id: 5, src: "/assets/digitalnotes.png", backlink: "https://digitalnotes.com", alt: "DigitalNotes" },
  { id: 6, src: "/assets/echo.png", backlink: "https://echovalley.net", alt: "Echo" },
  { id: 7, src: "/assets/alternativeoss.png", backlink: "https://alternativeoss.com", alt: "AlternativeOSS" },
]);

const logosContainerRef = ref(null);
const isPaused = ref(false);
let animationFrameId = null;
let scrollPosition = 0;
let singleSetWidth = 0;

// Animation loop function
function animate() {
  if (!isPaused.value && logosContainerRef.value) {
    scrollPosition -= 0.5; // Adjust speed here
    
    // Reset position for seamless loop when the first set of logos moves out of view
    if (Math.abs(scrollPosition) >= singleSetWidth) {
      scrollPosition = 0;
    }
    
    logosContainerRef.value.style.transform = `translateX(${scrollPosition}px)`;
  }
  animationFrameId = requestAnimationFrame(animate);
}

// Function to ensure we have enough logos to fill the screen width
function ensureFullWidthCoverage() {
  if (!logosContainerRef.value) return;
  
  // Get viewport width
  const viewportWidth = window.innerWidth;
  
  // Get current width of logos container
  const containerWidth = logosContainerRef.value.scrollWidth;
  
  // If container width is less than 3x viewport width, add more logo duplicates
  if (containerWidth < viewportWidth * 3) {
    // This is handled statically in the template by adding a third set of logos
    // Could be made dynamic here if needed
  }
}

onMounted(() => {
  if (logosContainerRef.value) {
    // Calculate the width of a single set of logos (one-third of the total width since we now have three sets)
    singleSetWidth = logosContainerRef.value.scrollWidth / 3;
    
    // Ensure we have enough logos to cover full screen width
    ensureFullWidthCoverage();
    
    // Start animation
    animationFrameId = requestAnimationFrame(animate);
    
    // Add event listeners for hover effect
    logosContainerRef.value.addEventListener('mouseenter', () => {
      isPaused.value = true;
    });
    
    logosContainerRef.value.addEventListener('mouseleave', () => {
      isPaused.value = false;
    });
    
    // Handle window resize
    window.addEventListener('resize', ensureFullWidthCoverage);
  }
});

onBeforeUnmount(() => {
  // Clean up animation
  if (animationFrameId) {
    cancelAnimationFrame(animationFrameId);
  }
  
  // Remove resize listener
  window.removeEventListener('resize', ensureFullWidthCoverage);
});
</script>

<style scoped>
.logos-container {
  will-change: transform;
  white-space: nowrap;
}

.logo-image {
  filter: invert;
}

.group:hover .logo-image {
  filter: invert(11%) sepia(66%) saturate(1857%) hue-rotate(187deg) brightness(93%) contrast(101%);
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-33.33%); /* Only need to scroll one-third since we have three sets */
  }
}

/* Fallback animation if the JavaScript animation fails */
@media (prefers-reduced-motion: no-preference) {
  .logos-container {
    animation: scroll 20s linear infinite;
  }
  
  .logos-container:hover {
    animation-play-state: paused;
  }
}
</style>