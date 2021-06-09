<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
   Header,
   Main
  }
}
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
   *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    }
    #app {
      background-color: #1e2d3b;
      padding-bottom: 50px;
    }
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500;600;700&family=Roboto:wght@500;700&display=swap');

</style>
