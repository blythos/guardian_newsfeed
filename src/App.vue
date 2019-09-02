<template>
  <div id="app">
    <header-bar />
    <tags-list />
    <articles-list :results="results" />
  </div>
</template>

<script>
import TagsList from '@/components/TagsList';
import HeaderBar from '@/components/HeaderBar';
import ArticlesList from '@/components/ArticlesList'

import {eventBus} from '@/main.js';

export default {
  name: 'app',
  components: {
    TagsList,
    HeaderBar,
    ArticlesList
  },
  data() {
    return {
      selectedKeyword: null,
      results: null
    }
  },
  mounted() {
    eventBus.$on('results-selected', (results) => {
      this.results = results.then(res => res.json()).then(data => this.results = data.response.results);
    })
  }
}
</script>

<style lang="css">
  #app {
    font-family: sans-serif;
  }
</style>
