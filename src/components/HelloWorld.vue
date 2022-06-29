<template>
  <b-container>
    <h3>Login</h3>
      <hr>  
      <b-row class="justify-content-md-center">

        <b-form @submit.prevent="login" style="width:400px">
          <b-form-group label-for="email">
            <b-form-input
            id="email"
            type="email"
            required
            v-model="email"
            placeholder="Email"
            ></b-form-input>
          </b-form-group>

          <b-form-group label-for="password">
            <b-form-input
            id="password"
            required
            v-model="password"
            placeholder="Password"
            ></b-form-input>
          </b-form-group>

          <b-button type="submit" block-variant="primary">Ingresar</b-button>
        </b-form>

      </b-row>

      <hr>
    <small>&copy; Irpiri Code</small>
  </b-container>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    email: '',
    password: '',
  }),
  methods: {
    login(){
      let url = 'http://127.0.0.1:3333/login'

      this.axios.post(url, {
        email:this.email, password:this.password
      }
     ).then(response => {
        console.log(response.data)
     })
    }
  }
}
</script>

<style lang="scss" scoped>

</style>