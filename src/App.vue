<script setup>
import Header from "./components/Header.vue";
import PostComponent from "./components/PostComponent.vue";
import Navigation from "./components/Navigation.vue";
</script>

<template>
  <header class="header">
    <Header />
    <font-awesome-icon icon="phone" />
    <Navigation />
  </header>

  <main>
    <PostComponent />
  </main>
</template>

<style scoped>
main {
  display: grid;
  grid-template-rows: (2, 1fr);
  max-width: 1280px;
  margin-top: 100px;
}
.header {
  position: fixed;
  top: 0;
  display: flex;
  flex-direction: column;
  width: 100%;
  z-index: 1;
  max-width: 1280px;
  margin-left: -20px;
}
</style>
