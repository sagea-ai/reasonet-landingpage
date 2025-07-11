<template>
  <div class="bg-white px-6 py-12 md:px-8 md:mx-12">
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
      <!-- Left Side -->
      <div>
        <!-- FAQ Header -->
        <div class="text-[15px] font-medium text-[#6B7280] mb-3">FAQ</div>

        <!-- Question Header -->
        <h1 class="text-[32px] font-bold text-[#111827] mb-3">Have a question?</h1>

        <!-- Description Text -->
        <p class="text-[15px] leading-[24px] text-[#4B5563] mb-8">
          We have collected the most frequently asked questions about Reasonet. If you have a question that isn't answered here, feel free to reach out to us.
        </p>

        <!-- Get in touch button -->
        <a href="mailto:support@reasonet.ai">
        <button
          class="w-content inline-flex items-center px-4 py-3 border border-[#D1D5DB] rounded-full shadow-sm hover:bg-gray-50 transition-colors"
          
        >
          <svg
            class="w-[18px] h-[18px] mr-2 text-[#6B7280]"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M8 12H8.01M12 12H12.01M16 12H16.01M21 12C21 16.4183 16.9706 20 12 20C10.4607 20 9.01172 19.6565 7.74467 19.0511L3 20L4.39499 16.28C3.51156 15.0423 3 13.5743 3 12C3 7.58172 7.02944 4 12 4C16.9706 4 21 7.58172 21 12Z"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
          <span class="text-sm font-medium text-[#374151]">Get in touch</span>

        </button>
        </a>
      </div>

      <!-- Right Side -->
      <div>
        <!-- FAQ Items -->
        <div class="border-t border-[#E5E7EB]">
          <button
            class="w-full flex justify-between items-center py-5 text-left"
            @click="toggleFaq(0)"
          >
            <span class="text-[15px] text-[#111827] font-medium">What does Reasonet do?</span>
            <svg
              class="w-5 h-5 text-[#6B7280] transform transition-transform duration-200"
              :class="{ 'rotate-180': openIndex === 0 }"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>
          <div
            v-show="openIndex === 0"
            class="pb-5 text-[15px] leading-[24px] text-[#4B5563]"
          >
            Reasonet is a strategic reasoning engine that helps founders stress-test ideas, simulate investor reactions, and identify blind spots in their business plans.
          </div>
        </div>

        <div class="border-t border-[#E5E7EB]">
          <button
            class="w-full flex justify-between items-center py-5 text-left"
            @click="toggleFaq(1)"
          >
            <span class="text-[15px] text-[#111827] font-medium"
              >How is Reasonet different from ChatGPT?</span
            >
            <svg
              class="w-5 h-5 text-[#6B7280] transform transition-transform duration-200"
              :class="{ 'rotate-180': openIndex === 1 }"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>
          <div
            v-show="openIndex === 1"
            class="pb-5 text-[15px] leading-[24px] text-[#4B5563]"
          >
            Unlike generic AI chatbots, Reasonet thinks like an investor and advisor, providing actionable feedback and simulating real-world responses to your startup ideas.
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FAQSection',
  data() {
    return {
      openIndex: null,
    }
  },
  methods: {
    toggleFaq(index) {
      this.openIndex = this.openIndex === index ? null : index
    },
  },
}
</script>

<style scoped>
/* Add any additional styles if necessary */
</style>
