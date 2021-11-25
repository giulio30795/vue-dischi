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
  height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
