<script setup>
import { reactive } from "vue";

const state = reactive({
  listItems: [],
  loading: false,
  nextItem: 1,
  busy: false,
});
function getPosts() {
  state.busy = true;
  fetch(
    "https://newsapi.org/v2/everything?domains=wsj.com&apiKey=22fa0a73b7ce45e68300a153ed853db4"
  )
    .then((response) => response.json(10))
    .then((data) => {
      state.listItems = data.articles;
      state.busy = false;
      console.log(data);
    });
}

getPosts();
</script>
<template>
  <div class="wrapper">
    <section class="news">
      <div
        v-for="(listItem, idx) in state.listItems"
        :key="listItem.id"
        class="news__block"
        :class="{ 'news__block--first': !idx }"
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
  margin-top: 100px;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: auto;
  gap: 30px;
  grid-template-areas: "first first";
}
h2 {
  font-family: SpiegelSlabCdUI, Constantia, Lucida Bright, Lucidabright,
    Lucida Serif, Lucida, DejaVu Serif, Bitstream Vera Serif, Liberation Serif,
    Georgia, serif;
}
.news__block--first {
  grid-area: first;
  display: flex;
  flex-direction: column;
}
.news__text {
  order: 1;
}
.news__block--first img {
  max-width: 100%;
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
  padding: 20px;
}
</style>
