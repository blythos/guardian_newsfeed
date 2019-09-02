<template lang="html">
<div class="listview">
<ul>
  <tag-item v-for="keyword in keywords" :keyword="keyword" />
</ul>
</div>
</template>

<script>
import TagItem from '@/components/TagItem'
export default {
  name: 'tags-list',
  data() {
    return {
      keywords: ["brexit", "politics"],
    }
  },
  components: {
    TagItem
  }
}
</script>

<style lang="css" scoped>
</style>
