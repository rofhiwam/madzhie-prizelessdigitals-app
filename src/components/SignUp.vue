<template>
    <b-form @submit="onSubmit">
         <b-form-group :sign-up-error="signUpError">
            <h2>Register</h2>
            <p>Name</p>
            <b-form-input v-model="username" type="text" required/>
        </b-form-group>
         <b-form-group :sign-up-error="signUpError">
            <p>Phone number</p>
            <b-form-input v-model="username" type="text" required/>
        </b-form-group>
        <b-form-group :sign-up-error="signUpError">
            <p>Email address</p>
            <b-form-input v-model="username" type="text" required/>
        </b-form-group>

        <b-form-group>
            <p>Password</p>
            <b-form-input v-model="password" type="password" required/>
        </b-form-group>

        <div class="text-center">
            <b-button type="submit" variant="primary" block>Register</b-button>
        </div>
    </b-form>
</template>

<script>
export default {
    data(){
        return{
            username: '',
            password: '',
            signUpError: ''
        }
    },
    methods: {
        onSubmit (){
            this.$emit('login')
        }
    }
}
</script>
