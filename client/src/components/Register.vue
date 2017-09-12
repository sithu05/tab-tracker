<template lang="html">
  <div class="register">
    <h1>Register</h1>

    <input type="email" name="email" placeholder="Email" v-model="email"><br>
    <input type="password" name="password" placeholder="password" v-model="password"><br>

    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  name: 'register',

  data () {
    return {
      email: 'abc@abc.com',
      password: '123'
    }
  },

  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })

      console.log(response.data)
    }
  }
}
</script>

<style lang="css">
</style>
