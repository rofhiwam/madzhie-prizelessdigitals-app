<template>
  <div>
    <b-container v-if="!logedIn">
      <b-row align-v="center" style="min-height: 90vh;">
        <b-col>
          <authentication-parent @login="logedIn = true" @async-start="asyncState= true" @async-end="asyncState = false"/>
        </b-col>
      </b-row>
    </b-container>
    <dashboard-page v-else @log-out="logedIn = false" @async-start="asyncState = true" @async-end="asyncState = false"/>
  </div>
</template>

<script>
import AuthenticationParent from './components/AuthenticationParent'
import DashboardPage from './components/Dashboard'
export default {
  data(){
    return{
      asyncState: false,
      logedIn: false
    }
  },
  components:{
    AuthenticationParent,
    DashboardPage
  }
}
</script>
