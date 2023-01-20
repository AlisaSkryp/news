<script setup>
import { reactive } from "vue";

const state = reactive({
  listItems: [],
  busy: false,
});

function fetchData() {
  state.busy = true;
  fetch(
    "https://newsapi.org/v2/everything?q=tesla&from=2022-12-20&sortBy=publishedAt&apiKey=22fa0a73b7ce45e68300a153ed853db4"
  )
    .then((response) => response.json())
    .then((data) => {
      state.listItems = data.articles;
      state.busy = false;
      console.log(data);
    });
}
fetchData();
</script>
<template>
  <div class="wrapper">
    <section class="news">
      <div
        v-for="listItem in state.listItems"
        :key="listItem.id"
        class="news__block"
      >
        <div class="news__text">
          <h2>{{ listItem.title }}</h2>
          <p>{{ listItem.content }}</p>
        </div>
        <img :src="listItem.urlToImage" alt="" />
      </div>
    </section>
  </div>
</template>
<style>
.news {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
}
.news__block {
  background-color: rgb(44, 44, 44);
  margin: 0 auto;
}
.news__text {
  padding: 20px;
}
img {
  max-width: 600px;
  height: auto;
}
li {
  background-color: palevioletred;
  color: black;
}
</style>
