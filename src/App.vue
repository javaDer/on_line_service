<template>
  <div id="app">
    <app-header></app-header>
    <!--<transition name="router-fade">-->
    <!--<router-view></router-view>-->
    <!--</transition>-->
    <router-view/>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import AppHeader from "./components/header"
  import AppFooter from "./components/footer"
  export default {
    components: {
      AppHeader,
      AppFooter
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
