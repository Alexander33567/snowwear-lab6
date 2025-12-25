<template>
  <div>
    <AppHeader />
    <main id="home">
      <HeroSection />
      <CatalogSection />
      <LoginSection />
    </main>
  </div>
</template>

<script setup>
import AppHeader from "./components/AppHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import CatalogSection from "./components/CatalogSection.vue";
import LoginSection from "./components/LoginSection.vue";
</script>
