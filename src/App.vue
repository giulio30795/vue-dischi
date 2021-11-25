<template>
  <div id="app">
    <Header />
    <MainContent />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    Header,
    MainContent,
  }
}
</script>
<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
#app{
  background-color: #1d2d3c;
}
</style>
