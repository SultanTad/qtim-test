<script setup lang="ts">
import { ref, onMounted, computed } from "vue";
import type { Ref } from "vue";
import axios from "axios";

interface Article {
  id: number;
  image: string;
  description: string;
}

const allArticles: Ref<Article[]> = ref([]);
const page: Ref<number> = ref(1);

const getArticles = async () => {
  const res = await axios.get(
    "https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/"
  );
  allArticles.value = res.data;
};

const currentArticles = computed(() => {
  return allArticles.value.filter((article, index) => {
    return index <= page.value * 8 && index > (page.value - 1) * 8;
  });
});

const allPages = computed((): number => {
  if (allArticles.value.length) {
    console.log(allArticles.value.length / 8);
    return Math.ceil(allArticles.value.length / 8);
  } else return 0;
});

onMounted(async () => {
  await getArticles();
});
</script>

<template>
  <TheHeader />
  <main class="main">
    <div class="container">
      <h1 class="main__title">Articles</h1>
      <ul class="articles__list">
        <li
          class="articles__item"
          v-for="article in currentArticles"
          :key="article.id"
        >
          <div class="articles__item-inner">
            <img class="articles__item-img" :src="article.image" alt="" />
            <p class="articles__item-text">{{ article.description }}</p>
            <NuxtLink
              :to="{ name: 'article-id', params: { id: article.id } }"
              class="articles__item-subtext"
              >Read more</NuxtLink
            >
          </div>
        </li>
      </ul>
      <div class="pagination">
        <button class="pagination__btn"@click="page = item" v-for="item in allPages">
          {{ item }}
        </button>
        <img class="pagination__arrow" @click="page++" src="../assets/images/icons.png" alt="" />
      </div>
    </div>
  </main>
  <TheFooter />
</template>

<style>
.main {
  font-family: "TTCommons-Regular";
}

.articles__list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 40px 32px;
  margin-top: 60px;
}

.articles__list img {
  width: 280px;
  margin-bottom: 24px;
}

.articles__item-text {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  font-size: 20px;
  line-height: 24px;
}

.articles__item-subtext {
  color: #e2beff;
  font-size: 20px;
  line-height: 24px;
  transition: all 0.3s ease-in-out;
  visibility: hidden;
  opacity: 0;
  margin-top: 25px;
}

.articles__item-inner {
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

.articles__item-inner:hover {
  transform: translateY(-24px);
  transition: all 0.3s ease-in-out;
}

.articles__item-inner:hover .articles__item-subtext {
  transition: all 0.3s ease-in-out;
  visibility: visible;
  opacity: 1;
}

.main__title {
  font-size: 84px;
  line-height: 100%;
  font-weight: 400;
}

.pagination {
  margin-top: 50px;
  display: flex;
  gap: 0 8px;
}

.pagination button {
  padding: 11px 17px;
  border-radius: 12px;
  border: none;
  cursor: pointer;
  font-family: "TTCommons-Regular";
  font-size: 20px;
  font-weight: 400;
  line-height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.pagination button:active {
  background-color: #000;
  color: #fff;
}

.pagination img {
  width: 44px;
  height: 44px;
  border: 1px solid #e8e8e8;
  border-radius: 12px;
  cursor: pointer;
}
</style>
