<template lang="html">

</template>

<script>
export default {
  name: 'list-items',
  props: ['keywords'],
  mounted() {
    fetch(`https://content.guardianapis.com/search?q=${this.keywords[0]}&format=json&api-key=test&order-by=newest`)
    .then(res => res.json())
    .then(data => this.results = data.response.results)
  }
}
</script>

<style lang="css" scoped>
</style>
