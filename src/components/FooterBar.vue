<template>
  <footer class="bg-white pt-16 pb-8 px-6">
    <div class="max-w-[1200px] mx-auto">
      <!-- Logo and Description -->
      <div class="mb-12">
        <router-link to="/" class="inline-block">
          <div class="flex items-center">
            <img src="@/assets/logo.png" class="h-12 w-12 -mr-2 -ml-2" alt="Reasonet logo" />
            <span class="text-[20px] font-semibold ml-2">Reasonet</span>
          </div>
        </router-link>
        <p class="text-gray-600 mt-4 text-[15px]">
          Strategic Reasoning Engine for Founders & Policymakers.
        </p>
      </div>

      <!-- Footer Links Grid -->
      <!-- Remove footer links grid for single landing page -->
      <!-- Copyright -->
      <div class="pt-8 text-gray-600 text-[13px]">
        © {{ new Date().getFullYear() }} Reasonet, All rights reserved.
      </div>
    </div>
  </footer>
</template>

<script>
import { OhVueIcon as VIcon, addIcons } from "oh-vue-icons";
import { FaTwitter, FaLinkedin, FaInstagram, FaYoutube } from "oh-vue-icons/icons";

// Register the icons
addIcons(FaTwitter, FaLinkedin, FaInstagram, FaYoutube);

export default {
  name: "FooterBar",
  components: {
    VIcon
  }
};
</script>
