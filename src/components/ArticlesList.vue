<template lang="html">
  <div>
    <ul>
      <li v-for="(result, index) in this.results" :key="index" :result="result"><a :href="result.webUrl">{{result.webTitle}}</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'articles-list',
  props: ['results']
}
</script>

<style lang="css" scoped>
</style>
