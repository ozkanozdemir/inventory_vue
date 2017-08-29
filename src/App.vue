<template>
  <div id="app" class="">
    <app-navbar></app-navbar>
    <div class="container">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
  import Navbar from './components/partials/Navbar.vue'

  export default {
    name: 'app',
    components: {
      appNavbar: Navbar
    }
  }
</script>

<style lang="scss">
  @import "../node_modules/bootstrap/scss/bootstrap.scss";

  #app {

  }
</style>
