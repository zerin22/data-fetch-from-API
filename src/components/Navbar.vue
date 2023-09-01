<template>
  <nav class="navbar">
    <ul>
      <li v-for="item in navbarItems" :key="item.id">
        {{ item.name }}
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

const navbarItems = ref([]);

onMounted(async () => {
  const response = await axios.get(
      'https://basic-blog.teamrabbil.com/api/post-categories'
  );
  navbarItems.value = response.data;
});
</script>

<style scoped>
.navbar ul {
  display: flex;
  justify-content: center;
  list-style-type: none;
  gap:20px;
  margin: 0;
  padding: 0;
}

.navbar li {
  margin: 0 10px;
}
</style>
