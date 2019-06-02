<template>
  <b-form @submit="onSubmit">
      <b-form-group>
          <p>Email Address:</p>
          <b-form-input v-model="username" type="text" required/>
      </b-form-group>

      <b-form-group>
          <p>Password:</p>
          <b-form-input v-model="password" type="password" required/>
      </b-form-group>
      
      <b-form-group v-if="loginError == true">
          <p>Invalid login. Please make sure you entered the correct username and password.</p>
      </b-form-group>
    
      <div class="text-center">
          <b-button type="Submit" variant="primary" block>Sign In</b-button>
          <p>Not registered yet?</p>
          <b-button variant="link" @click="$emit('change-form')">Register here</b-button>
      </div>
  </b-form>
</template>

<script>
export default {
    data(){
        return{
            username: '',
            password: '',
            loginError: false
        }
    },
    methods: {
        onSubmit(e){

            if(this.username=='madzhier@gmail.com' && this.password=='Wh3nC@nI$tart'){
                this.$emit('login')
            }else{
                this.loginError = true
            }
            e.preventDefault();
        }
    }
}
</script>
