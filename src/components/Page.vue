<template>
  <div>
    <div v-for="item in pageContent" :key="item.id">
      <img :src="item.img" alt="item image" height="400" width="700" />
      <h2>{{ item.title }}</h2>
      <p>{{ item.short }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      pageContent: [],
    };
  },
  async created() {
    const response = await axios.get(
        'https://basic-blog.teamrabbil.com/api/post-list/2'
    );
    this.pageContent = response.data;
  },
};
</script>
