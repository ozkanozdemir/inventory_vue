<template>
  <nav class="navbar sticky-top navbar-toggleable-md navbar-light bg-faded">
    <div class="container">
      <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <router-link class="navbar-brand" :to="{name: 'home'}" exact>Inventory</router-link>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <router-link class="nav-item" :to="{name: 'home'}" tag="li" exact>
            <a class="nav-link">Home</a>
          </router-link>
          <router-link class="nav-item" :to="{name: 'login'}" tag="li">
            <a class="nav-link">Login</a>
          </router-link>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input class="form-control mr-sm-2" type="text" placeholder="Search">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>

</script>

<style scoped lang="scss">
  .navbar {
    background-color: linen;
  }
</style>
