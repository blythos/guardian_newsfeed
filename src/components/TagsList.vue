<template lang="html">
<div class="listview">
<ul>
  <li v-for="keyword in keywords">{{keyword}}</li>
</ul>
</div>
</template>

<script>
export default {
  name: 'tags-list',
  data() {
    return {
      keywords: ["brexit", "politics"],
    }
  },
  methods: {
      handeClick() {
        eventBus.$emit('keyword-selected', this.keyword);
      }
  },
  props: ['keyword']
}
</script>

<style lang="css" scoped>
</style>
