<template>
  <div id="app" class="container">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
  created () {
    let data = {
      client_id: 2,

    }
    this.$http.get('http://inventory.app/api/test')
      .then(response => {
        console.log(response)
      })
  }
}
</script>

<style>

</style>
