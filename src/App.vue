<template>
  <div id="app">
    <div>
      <header>
        <div class="container mx-auto">
          <Navbar />
        </div>
      </header>
      <main>
        <Page />
      </main>
    </div>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import Page from './components/Page.vue';
</script>

<style scoped>
.container{
  max-width: 1000px;
  margin: auto;
}
header {
  width: 100%;
}

main {
  margin-top: 20px;
}
</style>
