<script setup lang="ts">
import { ref, onMounted } from "vue";
import type { Ref } from "vue";
import axios from "axios";
import { useRoute } from "vue-router";

interface Article {
  title?: string;
  image?: string;
  description?: string;
}

const route = useRoute();
const article: Ref<Article> = ref({});

const getArticle = async () => {
  const res = await axios.get(
    `https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${route.params.id}`
  );
  article.value = res.data;
};

onMounted(async () => {
  await getArticle();
});
</script>

<template>
  <TheHeader />
  <section class="article">
    <div class="container">
      <h2 class="article__title">{{ article.title }}</h2>
      <img class="article__img" :src="article.image" alt="" />
      <h3 class="article__subtitle">About</h3>
      <p class="article__description">{{ article.description }}</p>
    </div>
  </section>
  <TheFooter />
</template>

<style>
.article {
  font-family: "TTCommons-Regular";
  font-weight: 400;
  margin-top: 119px;
  margin-bottom: 80px;
}

.article h2 {
  font-size: 84px;
  line-height: 84px;
  font-weight: 400;
  margin-bottom: 70px;
}

.article__img {
  width: 100%;
  height: 700px;
  object-fit: cover;
}

.article__subtitle {
  margin-top: 50px;
  margin-bottom: 32px;
  font-size: 16px;
  line-height: 16px;
  font-weight: 400;
}

.article__description {
  font-size: 36px;
  line-height: 44.64px;
}
</style>
