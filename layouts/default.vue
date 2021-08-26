<template>
  <div>
    <nav>
      <div class="navbar">
        <div v-if="user" class="user-name">
          <p>Hi, {{user.firstName}}</p>
        </div>
        <button v-if="!user" @click="login" class="login-btn">
         Login
        </button>
          <button v-if="user" @click="logout" class="login-btn">
         Logout
        </button>
      </div>
    </nav>

  <div class="container">
        <Nuxt />
  </div>

  </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      url: "https://interview-backend.herokuapp.com",
      user: null
    }; 
  },
  methods:{
   async login(){
      const res = await axios.post(this.url + "/user/login")
        if(res.data.success){
          this.getUserInfo()
        }
    },
     async logout(){
     await axios.post(this.url + "/user/logout")
        this.user = null;
    },
    async getUserInfo(){
        const result = await axios.get(this.url + "/user/me") 
        this.user = result.data.user
    }
  },
  mounted(){}
}
</script>


<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.navbar{
  background-color: #46659F;
  width: 100%;
  height: 40px;
  display: flex;
  align-content: center;
  justify-content: flex-end;
}

.login{
  width: 40px;
  margin-right: 40px;
}


.container{
  width: 50%;

}

.user-name{
  font-size: 16px;
  color: white;
  font-weight: 600;
  display: flex;
  align-items: center;
  margin-right: 24px;
}
</style>
