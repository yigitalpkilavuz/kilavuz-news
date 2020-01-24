<template>
  <div clas="container">
    <NavBar />
    <nuxt />
  </div>
</template>


<script>
import NavBar from '@/components/NavBar.vue'

export default {
  head() {
    return {
      title: 'Kilavuz News'
    }
  },
  components: {
    NavBar
  }
}
</script>


<style>
</style>
