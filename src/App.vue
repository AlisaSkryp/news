<script setup>
import Header from "./components/Header.vue";
import PostComponent from "./components/PostComponent.vue";
import ListComponent from "./components/ListComponent.vue";
</script>

<template>
  <header>
    <Header />
  </header>

  <main>
    <PostComponent />
    <ListComponent />
  </main>
</template>

<style scoped>
main {
  max-width: 1280px;
}
</style>
