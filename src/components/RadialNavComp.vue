<template>
  <div class="radial-nav">
    <div class="center-button" @click="toggleMenu">
      <img src="/favicon.png" alt="Menu" class="center-logo" />
    </div>
    <nav :class="{ menu: true, active: isOpen }">
      <li
        v-for="(icon, index) in icons"
        :key="index"
        :style="{ '--i': index }"
        class="menu-item"
        @click="navigateTo(icon.route)"
      >
        <Icon :icon="icon.name" />
      </li>
    </nav>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import { Icon } from '@iconify/vue';

const isOpen = ref(false);
const router = useRouter();

const icons = [
  { name: 'ion:home-outline', route: '/' },
  { name: 'ion:images-outline', route: '/gallery' },
  { name: 'ion:book-outline', route: '/memories' },
  { name: 'ion:information-circle-outline', route: '/about' },
];

const toggleMenu = () => {
  isOpen.value = !isOpen.value; // Bascule l'ouverture/fermeture du menu
};

const navigateTo = (route) => {
  router.push(route);
  isOpen.value = false; // Ferme le menu après navigation
};
</script>

<style scoped>
/* Styles de base pour la navigation radiale */
.radial-nav {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.center-button {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #f5f5dc; /* Couleur beige */
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background-color 0.3s, box-shadow 0.3s; /* Ajout de la transition pour l'ombre */
  position: relative;
  z-index: 1000;
  border: 4px solid rgba(255, 215, 0, 0.8); /* Bordure lumineuse en doré */
  box-shadow: 0 0 15px rgba(255, 215, 0, 0.5), 0 0 30px rgba(173, 216, 230, 0.7); /* Ombre céleste */
}

.center-logo {
  width: 30px;
  height: 30px;
}

.menu {
  position: absolute;
  width: 200px;
  height: 200px;
  display: none; /* Masqué par défaut */
  align-items: center;
  justify-content: center;
  background: transparent; /* Enlève le fond ici, car il est géré par les icônes */
}

.menu.active {
  display: flex; /* Affiché uniquement lorsque `isOpen` est vrai */
}

.menu-item {
  position: absolute;
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, rgba(173, 216, 230, 0.8), rgba(255, 255, 255, 0.3)); /* Dégradé céleste */
  color: #333;
  font-weight: bolder;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  font-size: 1.5rem;
  transition: transform 0.8s, box-shadow 0.3s; /* Ajoute une transition pour l'ombre */
  border: 2px solid rgba(255, 215, 0, 0.8); /* Bordure lumineuse pour les icônes */
  box-shadow: 0 0 10px rgba(255, 215, 0, 0.5), 0 0 20px rgba(173, 216, 230, 0.7); /* Ombre céleste pour les icônes */
}

/* Positions spécifiques pour chaque icône en mobile */
.menu-item:nth-child(1) { transform: rotate(-190deg) translate(100px) rotate(-170deg); }
.menu-item:nth-child(2) { transform: rotate(-150deg) translate(100px) rotate(-210deg); }
.menu-item:nth-child(3) { transform: rotate(-108deg) translate(100px) rotate(107deg); }
.menu-item:nth-child(4) { transform: rotate(-67deg) translate(100px) rotate(65deg); }

/* Position des icônes en bas à gauche en desktop */
@media (min-width: 1024px) {
  .menu-item:nth-child(1) { transform: rotate(70deg) translate(100px) rotate(-70deg); }
  .menu-item:nth-child(2) { transform: rotate(110deg) translate(100px) rotate(-110deg); }
  .menu-item:nth-child(3) { transform: rotate(150deg) translate(100px) rotate(-150deg); }
  .menu-item:nth-child(4) { transform: rotate(190deg) translate(100px) rotate(-190deg); }
}
</style>
