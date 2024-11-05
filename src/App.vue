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
  width: 100%;
  min-height: 100vh; /* Assure que l'application remplit tout l'écran */
}

#app-container-body {
  max-width: 1280px; /* Largeur maximale de l'application */
  margin: 0 auto; /* Centre l'application */
  padding: 20px; /* Ajoute un padding pour espacer le contenu des bords */
}

/* Responsive Styles */
@media (max-width: 768px) {
  #app-container-body {
    padding: 10px; /* Réduit le padding pour mobile */
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  #app-container-body {
    padding: 15px; /* Ajuste le padding pour les tablettes */
  }
}

@media (min-width: 1025px) {
  #app-container-body {
    margin-top: 15vh;
    padding-top: 0; /* Ajoute un padding pour espacer le contenu des bords */
    padding-bottom: 0; /* Ajoute un padding pour espacer le contenu des bords */
  }
}
</style>
