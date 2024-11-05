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
.radial-nav {
  position: relative;
  width: 100px;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.center-button {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #333;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background-color 0.3s;
  position: relative;
  z-index: 1000;
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
}

.menu.active {
  display: flex; /* Affiché uniquement lorsque `isOpen` est vrai */
}

.menu-item {
  position: absolute;
  width: 60px;
  height: 60px;
  background-color: #444;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  font-size: 1.5rem;
  transition: transform 0.8s;
  transform: translate(-50%, -50%) rotate(calc(45deg * var(--i))) translateX(100px);
}

.menu-item:hover {
  background-color: #666;
}

.menu-item svg {
  width: 35px;
  height: 35px;
  color: white;
}

.menu-item:nth-child(1) { transform: rotate(-190deg) translate(100px) rotate(-170deg); }
.menu-item:nth-child(2) { transform: rotate(-150deg) translate(100px) rotate(-210deg); }
.menu-item:nth-child(3) { transform: rotate(-108deg) translate(100px) rotate(107deg); }
.menu-item:nth-child(4) { transform: rotate(-67deg) translate(100px) rotate(65deg); }
</style>
