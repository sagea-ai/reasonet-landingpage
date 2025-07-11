<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavBar from '@/components/NavBar.vue'
import FooterBar from '@/components/FooterBar.vue'
</script>

<template>
  <NavBar/>
  <RouterView />
  <Footer>
    <FooterBar/>
  </Footer>
</template>

<style scoped>
#app{
  align-items: center;
}
</style>
