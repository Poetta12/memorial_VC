<template>
  <header class="header">
    <div class="logo-container">
      <img src="/favicon.png" alt="Logo Memorial" class="logo" />
    </div>
    <RadialNavComp class="radial-nav" />
  </header>
</template>

<script setup>
import { defineProps } from 'vue';
import RadialNavComp from "@/components/RadialNavComp.vue";

defineProps({
  initials: {
    type: String,
    default: "Memorial Vitor Costa", // Remplace par les initiales souhaitées
  },
});
</script>

<style scoped>
.header {
  position: fixed;
  bottom: 0; /* Positionne le header en bas de l’écran */
  width: 100%;
  height: 15vh;
  padding: 15px;
  background: rgba(255, 255, 255, 0.9);
  display: flex;
  align-items: center;
  justify-content: space-between; /* Place RadialNav à droite */
  box-shadow: 0 -2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  width: 40px;
  height: auto;
  margin-right: 10px;
}

.header-title {
  font-size: 1.5em;
  font-weight: bold;
  color: #444;
  margin: 0;
}

.radial-nav {
  position: relative;
  right: 10px; /* Ajuste la position */
}
</style>
