<template>
  <div id="app">
    <header-bar />
    <tags-list />
  </div>
</template>

<script>
import TagsList from '@/components/TagsList'
import HeaderBar from '@/components/HeaderBar'

export default {
  name: 'app',
  components: {
    TagsList,
    HeaderBar
  }
}
</script>

<style>
#app {

}
</style>
