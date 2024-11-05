<template>
  <div class="guestbook">
    <h1>Livre d’or</h1>
    <p>Laissez un message en mémoire de Vitor Costa.</p>

    <!-- Formulaire pour ajouter un message -->
    <form @submit.prevent="addMessage">
      <input
        type="text"
        v-model="newMessage.name"
        placeholder="Votre nom"
        required
      />
      <textarea
        v-model="newMessage.content"
        placeholder="Votre message"
        required
      ></textarea>
      <button type="submit">Envoyer</button>
    </form>

    <!-- Liste des messages -->
    <div class="messages">
      <h2>Messages</h2>
      <ul>
        <li v-for="(message, index) in messages" :key="index">
          <strong>{{ message.name }}</strong> : {{ message.content }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const messages = ref([
  { name: 'Alice', content: 'Un souvenir précieux de Vitor.' },
  { name: 'Bob', content: 'Vitor restera toujours dans nos cœurs.' },
]);

const newMessage = ref({ name: '', content: '' });

const addMessage = () => {
  if (newMessage.value.name && newMessage.value.content) {
    messages.value.push({ ...newMessage.value });
    newMessage.value = { name: '', content: '' }; // Réinitialise le formulaire
  }
};
</script>

<style scoped>
.guestbook {
  text-align: center;
  padding: 20px;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

form input,
form textarea {
  width: 80%;
  max-width: 500px;
  margin-bottom: 10px;
  padding: 10px;
  font-size: 1em;
}

form button {
  padding: 10px 20px;
  font-size: 1em;
  cursor: pointer;
}

.messages {
  margin-top: 30px;
  text-align: left;
}

.messages ul {
  list-style-type: none;
  padding: 0;
}

.messages li {
  padding: 10px;
  border-bottom: 1px solid #ccc;
  margin-bottom: 10px;
}
</style>
