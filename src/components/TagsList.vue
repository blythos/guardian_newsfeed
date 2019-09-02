<template lang="html">
<div class="listview">
  <p>Order by</p>
  <button @click="orderToggle">{{this.order}}</button>
<ul>
  <tag-item v-for="keyword in keywords" :order="order" :keyword="keyword" />
</ul>
</div>
</template>

<script>
import TagItem from '@/components/TagItem'
export default {
  name: 'tags-list',
  data() {
    return {
      keywords: ["brexit", "politics", "videogames", "phoebe waller-bridge", "killing eve", "steven universe"],
      order: 'newest'
    }
  },
  methods: {
    orderToggle() {
      if (this.order === 'newest') {
        this.order = 'relevance';
      } else {
        this.order = 'newest';
      }
    }
  },
  components: {
    TagItem
  }
}
</script>

<style lang="css" scoped>
</style>
