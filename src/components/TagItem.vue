<template lang="html">
<ul @click="handeClick">
  {{this.keyword}}
</ul>
</template>

<script>
import {eventBus} from '@/main.js'
export default {
  name: 'tag-item',
  props: ['keyword'],
  methods: {
      handeClick() {
        eventBus.$emit('keyword-selected', this.keyword);
      }
  }
}
</script>

<style lang="css" scoped>
</style>
