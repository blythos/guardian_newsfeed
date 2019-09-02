<template>
  <div id="app">
    <header-bar />
    <tags-list />
    <articles-list />
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
      selectedKeyword: null
    }
  },
  mounted() {
    eventBus.$on('keyword-selected', (keyword) => {
      this.selectedKeyword = keyword;
      console.log(this.selectedKeyword);
    })
  }
}
</script>

<style lang="css">
  #app {
    font-family: sans-serif;
  }
</style>
