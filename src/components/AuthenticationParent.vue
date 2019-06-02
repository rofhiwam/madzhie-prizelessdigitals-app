<template>
    <b-container>
        <b-row align-h="center">
            <b-col cols="6">
                <sign-in v-if="wantLogin" @change-form="changeForm" @login="$emit('login')"/>
                <sign-up v-else @change-form="changeForm" @sign-up="$emit('sign-up')"/>
            </b-col>
        </b-row>
    </b-container>
</template>

<script>
import SignIn from './SignIn'
import SignUp from './SignUp'

export default {
    data(){
        return{
            wantLogin: true
        }
    },
    methods:{
       changeForm(){
           this.wantLogin = !this.wantLogin
       } 
    },
    components:{
        SignIn,
        SignUp
    }   
}
</script>
