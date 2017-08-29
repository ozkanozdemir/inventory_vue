<template>
  <div class="login">
    <h1>Login Page</h1>
    <hr>
    <form class="form-inline" @submit.prevent="submitForm">
      <div class="input-group mb-2 mr-sm-2 mb-sm-0">
        <div class="input-group-addon">@</div>
        <input type="email" v-model="email" class="form-control" placeholder="Email">
      </div>

      <div class="input-group mb-2 mr-sm-2 mb-sm-0">
        <div class="input-group-addon">***</div>
        <input type="password" v-model="password" class="form-control" placeholder="Password">
      </div>

      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
  import { loginUrl, userUrl, getHeaders } from '../config'
  import { clientId, clientSecret } from '../env'

  export default {
  name: 'login',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  created () {

  },
  methods: {
    submitForm () {
      let data = {
        client_id: clientId,
        client_secret: clientSecret,
        grant_type: 'password',
        username: this.email,
        password: this.password,
        scope: ''
      }

      const authUser = {}
      this.$http.post(loginUrl, data)
        .then(response => {
          if (response.status === 200) {
            console.log(response)
            authUser.access_token = response.data.access_token
            authUser.refresh_token = response.data.refresh_token
            window.localStorage.setItem('authUser', JSON.stringify(authUser))

            this.$http.get(userUrl, { headers:getHeaders() })
              .then(response => {
                console.log(response)
                authUser.email = response.data.email
                authUser.name = response.data.name
                window.localStorage.setItem('authUser', JSON.stringify(authUser))
                this.$router.push({ name: 'home' })
              })
          }
        })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
