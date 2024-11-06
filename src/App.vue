<template>
  <div id="app-container">
    <HeaderComp :initials="'Vitor Costa'" />
    <div id="app-container-body">
      <RouterView />
    </div>
  </div>
</template>

<script setup>
import HeaderComp from "@/components/HeaderComp.vue";
import { RouterView } from 'vue-router';
</script>

<style scoped>
#app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  min-height: 100vh; /* Assure que l'application remplit tout l'écran */
}

#app-container-body {
  padding: 20px; /* Ajoute un padding pour espacer le contenu des bords */
}

@media (min-width: 1025px) {
  #app-container-body {
    max-width: 1280px;
    width: 100%;
    margin-top: 15vh;
    padding-top: 0; /* Ajoute un padding pour espacer le contenu des bords */
    padding-bottom: 0; /* Ajoute un padding pour espacer le contenu des bords */
  }
}
</style>
