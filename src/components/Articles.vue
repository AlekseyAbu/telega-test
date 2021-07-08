<template>
  <div>
    <div class="articles">
      <img class="articles__img" :src="article.articles.article1.image" alt="#" />
      <p class="articles__text articles__text-right">{{ article.articles.article1.text }}</p>
    </div>
    <div class="articles">
        <p class="articles__text articles__text-left">{{article.articles.article2.text}}</p>
        <img class="articles__img" :src='article.articles.article2.image' alt="#">
    </div>
  </div>
</template>

<script>
export default {
  props: ["article"],
};
</script>

<style scoped>
.articles {
  padding: 0 20px 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.articles__img {
  width: 100px;
  height: 100px;
}
.articles__text {
  max-width: 200px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 10px;
  line-height: 12px;
  text-align: justify;
}
@media screen and (max-width: 350px) {
    .articles__text-right{
        margin-left: 15px;
    }
    .articles__text-left{
        margin-right: 15px;
    }
}
</style>