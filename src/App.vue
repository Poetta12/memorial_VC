<template>
  <div id="app-container">
    <HeaderComp @headerPositionChanged="setFooterPosition" :initials="'Vitor Costa'" />
    <div id="app-container-body">
      <RouterView />
    </div>
    <Footer :isHeaderBottom="isHeaderBottom" />
  </div>
</template>

<script setup>
import HeaderComp from "@/components/HeaderComp.vue";
import Footer from "@/components/FooterComp.vue"; // Assurez-vous d'importer le Footer
import { ref } from 'vue';
import { RouterView } from 'vue-router';

const isHeaderBottom = ref(false);

// Fonction pour mettre à jour l'état de la position de l'en-tête
const setFooterPosition = (isBottom) => {
  isHeaderBottom.value = isBottom;
};
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
  flex-grow: 1; /* Permet à ce conteneur de prendre tout l'espace disponible entre l'en-tête et le pied de page */
}

@media (min-width: 1025px) {
  #app-container-body {
    max-width: 1280px;
    width: 100%;
    margin-top: 15vh;
    padding-top: 0; /* Ajuste le padding */
    padding-bottom: 0; /* Ajuste le padding */
  }
}
</style>
