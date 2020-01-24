
<template></template>


<script>
export default {
  async asyncData({ $axios }) {
    var url =
      'https://newsapi.org/v2/top-headlines?' +
      'country=us&' +
      'apiKey=52b018cc23344e4f858647f24813a7d5'
    const articles = await $axios.$get(url)
    return { articles }
  },

  data() {
    return {
      url: this.$route.params.url
    }
  }
}
</script>


<style scoped>
</style>