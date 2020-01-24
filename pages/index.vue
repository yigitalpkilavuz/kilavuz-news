<template>
  <div class="container">
    <div class="row">
      <div
        class="col-12 col-md-6 col-lg-4"
        v-for="(article,index) in articles.articles"
        :key="index"
      >
        <div class="card">
          <img :src="article.urlToImage" class="card-img-top" />
          <div class="card-body">
            <h5 class="card-title">{{article.title}}</h5>
            <p class="card-text max-lines">{{article.description}}</p>
            <a :href="article.url" target="_blank">
              <h6>read more...</h6>
            </a>
            <p class="card-text">
              <small class="text-muted">{{ $moment(article.publishedAt).fromNow() }}</small>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    var url =
      'https://newsapi.org/v2/top-headlines?' +
      'country=us&' +
      'apiKey=52b018cc23344e4f858647f24813a7d5'
    const articles = await $axios.$get(url)
    return { articles }
  }
}
</script>

<style>
.card {
  margin-top: 10px;
}

.card-img-top {
  max-height: 250px;
}
.max-lines {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
}
</style>
