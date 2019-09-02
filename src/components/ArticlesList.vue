<template lang="html">
  <div>
    <ul>
      <li v-if="keyword" v-for="(result, index) in this.results" :key="index" :result="result">{{result.webTitle}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'articles-list',
  data() {
    return {
      results: null
    }
  },
  props: ['keyword'],
  mounted() {
    fetch(`https://content.guardianapis.com/search?q=${this.keyword}&format=json&api-key=test&order-by=newest`)
    .then(res => res.json())
    .then(data => this.results = data.response.results)
  }
}
</script>

<style lang="css" scoped>
</style>
