<template lang="html">
    <ul @click="handleClick">
      {{this.keyword}}
    </ul>
</template>

<script>
import {eventBus} from '@/main.js'
export default {
  name: 'tag-item',
  props: ['keyword', 'order'],
  methods: {
    handleClick() {
      eventBus.$emit('results-selected',
      fetch(`https://content.guardianapis.com/search?q=${this.keyword}&format=json&api-key=test&order-by=${this.order}`)
      );
    },
  }
}
</script>

<style lang="css" scoped>
  ul {
    cursor: pointer;
    color: grey;
    text-decoration: underline;
  }
</style>
