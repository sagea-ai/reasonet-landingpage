<template>
  <section class="bg-[#000014] text-[#FDFDFD] py-24 px-6 overflow-hidden relative">
    <!-- Background grid pattern -->
    <div class="absolute inset-0 opacity-5">
      <div class="grid-pattern"></div>
    </div>
    
    <!-- Gradient orbs -->
    <div class="absolute top-1/4 -left-20 w-64 h-64 bg-[#0043F1]/20 rounded-full blur-3xl"></div>
    <div class="absolute bottom-1/4 -right-20 w-96 h-96 bg-[#002C58]/20 rounded-full blur-3xl"></div>
    
    <div class="max-w-[1200px] mx-auto relative z-10">
      <!-- Header with animation -->
      <div ref="header" class="text-center mb-24 opacity-0">
        <p class="inline-block text-transparent bg-clip-text bg-gradient-to-r from-[#80A1F8] to-[#0043F1] font-medium mb-3">How it works</p>
        <h2 class="text-4xl font-bold">It only takes <span class="text-transparent bg-clip-text bg-gradient-to-r from-[#80A1F8] to-[#0043F1]">3 steps</span></h2>
      </div>

      <!-- Steps Grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-16 md:gap-8 mb-24">
        <!-- Step 1 -->
        <div ref="step1" class="text-center relative group opacity-0">
          <div class="absolute -inset-4 rounded-xl bg-gradient-to-r from-[#0043F1]/10 to-[#0043F1]/5 opacity-0 group-hover:opacity-100 blur transition-all duration-500"></div>
          <div class="step-number text-[140px] md:text-[180px] font-black leading-none mb-8 text-[#FDFDFD]">1</div>
          <div class="step-content relative">
            <div class="step-icon mb-6 mx-auto bg-gradient-to-br from-[#0043F1] to-[#002C58] w-16 h-16 rounded-2xl flex items-center justify-center shadow-lg transform group-hover:scale-110 transition-transform duration-500">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7v8a2 2 0 002 2h6M8 7V5a2 2 0 012-2h4.586a1 1 0 01.707.293l4.414 4.414a1 1 0 01.293.707V15a2 2 0 01-2 2h-2M8 7H6a2 2 0 00-2 2v10a2 2 0 002 2h8a2 2 0 002-2v-2" />
              </svg>
            </div>
            <h3 class="text-2xl font-semibold mb-4">Enter your idea</h3>
            <p class="text-[#EAEAEA] text-lg leading-relaxed">
              Describe your startup, problem, GTM, and vision. Reasonet works with any early-stage idea.
            </p>
          </div>
        </div>

        <!-- Step 2 -->
        <div ref="step2" class="text-center relative group opacity-0">
          <div class="absolute -inset-4 rounded-xl bg-gradient-to-r from-[#80A1F8]/10 to-[#80A1F8]/5 opacity-0 group-hover:opacity-100 blur transition-all duration-500"></div>
          <div class="step-number text-[140px] md:text-[180px] font-black leading-none mb-8 text-[#FDFDFD]">2</div>
          <div class="step-content relative">
            <div class="step-icon mb-6 mx-auto bg-gradient-to-br from-[#80A1F8] to-[#0043F1] w-16 h-16 rounded-2xl flex items-center justify-center shadow-lg transform group-hover:scale-110 transition-transform duration-500">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" />
              </svg>
            </div>
            <h3 class="text-2xl font-semibold mb-4">Simulate feedback</h3>
            <p class="text-[#EAEAEA] text-lg leading-relaxed">
              Reasonet challenges your thesis, simulates investor/advisor reactions, and finds blind spots.
            </p>
          </div>
        </div>

        <!-- Step 3 -->
        <div ref="step3" class="text-center relative group opacity-0">
          <div class="absolute -inset-4 rounded-xl bg-gradient-to-r from-[#002C58]/10 to-[#002C58]/5 opacity-0 group-hover:opacity-100 blur transition-all duration-500"></div>
          <div class="step-number text-[140px] md:text-[180px] font-black leading-none mb-8 text-[#FDFDFD]">3</div>
          <div class="step-content relative">
            <div class="step-icon mb-6 mx-auto bg-gradient-to-br from-[#002C58] to-[#0043F1] w-16 h-16 rounded-2xl flex items-center justify-center shadow-lg transform group-hover:scale-110 transition-transform duration-500">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-2xl font-semibold mb-4">Get actionable insights</h3>
            <p class="text-[#EAEAEA] text-lg leading-relaxed">
              Receive counter-arguments, scores, and next steps—so you can build with confidence.
            </p>
          </div>
        </div>
      </div>

      <!-- Bottom Text and CTA -->
      <div ref="cta" class="text-center opacity-0">
        <p class="text-[#EAEAEA] text-lg mb-8">You set it up once – then Reasonet helps you iterate and improve.</p>
        <router-link to="/">
          <button 
            class="relative group bg-[#FDFDFD] text-[#000014] px-8 py-4 rounded-full font-medium shadow-xl shadow-[#FDFDFD]/20 hover:shadow-[#FDFDFD]/30 transition-all duration-300 overflow-hidden"
          >
            <span class="absolute top-0 left-0 w-full h-full bg-[#F3F3F3] opacity-0 group-hover:opacity-100 transition-opacity duration-300"></span>
            <span class="relative flex items-center">
              Try Reasonet
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </span>
          </button>
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';

// References to elements we want to animate
const header = ref(null);
const step1 = ref(null);
const step2 = ref(null);
const step3 = ref(null);
const cta = ref(null);

onMounted(() => {
  // Simple animation function using standard Web APIs
  const animateElement = (element, delay) => {
    setTimeout(() => {
      if (element.value) {
        element.value.style.opacity = '1';
        element.value.style.transform = 'translateY(0)';
      }
    }, delay);
  };

  // Apply initial styles programmatically
  [header.value, step1.value, step2.value, step3.value, cta.value].forEach(el => {
    if (el) {
      el.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
      el.style.transform = 'translateY(40px)';
    }
  });

  // Trigger animations with delays
  animateElement(header, 100);
  animateElement(step1, 300);
  animateElement(step2, 500);
  animateElement(step3, 700);
  animateElement(cta, 900);
});
</script>

<style scoped>
.grid-pattern {
  background-size: 40px 40px;
  background-image: 
    linear-gradient(to right, rgba(253, 253, 253, 0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(253, 253, 253, 0.05) 1px, transparent 1px);
  height: 100%;
}

.step-number {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  text-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-15px);
  }
  100% {
    transform: translateY(0px);
  }
}

.step-content {
  position: relative;
  z-index: 10;
}

.step-icon {
  animation: float 6s ease-in-out infinite;
}

/* Ensure each step has a different animation delay */
.step-icon:nth-of-type(1) {
  animation-delay: 0s;
}
.step-icon:nth-of-type(2) {
  animation-delay: 2s;
}
.step-icon:nth-of-type(3) {
  animation-delay: 4s;
}
</style>