<template>
  <div class="login-page">
    <div class="logo-container">
      <PageLogo/>
    </div>
    <div class="login-container">
      <h2>Log In</h2>
      <form @submit="login">
        <div class="form-group">
          <label for="name">Username</label>
          <input type="text" id="name" v-model="name" required placeholder="Enter Your Username">
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input type="password" id="password" v-model="password" required placeholder="Enter Your Password">
        </div>
        <div class="form-group">
          <div v-if="showErrorMessage" class="error-message">
            Please enter a valid search query.
          </div>
          <p class="forgot-password-link">
            <router-link to="/forgot-password">Forgot Password?</router-link>
          </p>
        </div>
        <button @:on-click="goToHome">Log In</button>
      </form>
      <div class="social-icons">
          <a href="#" class="icon"><i class="fab fa-google fa-3x"></i></a>
          <a href="#" class="icon"><i class="fab fa-facebook fa-3x"></i></a>
          <a href="#" class="icon"><i class="fab fa-linkedin fa-3x"></i></a>
      </div>
    </div>
    <div class="no-account" @click="goToSignUp">
            <p>Have You Registered an Account?</p>
        </div>
  </div>
</template>

<script>
import PageLogo from '@/components/PageLogo.vue'

export default {
  components: {
    PageLogo
  },
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login (event) {
      event.preventDefault()
      if (this.name && this.password) {
        console.log('Email:', this.name)
        console.log('Password:', this.password)
        this.name = ''
        this.password = ''
        this.$router.push('/')
      } else {
        // Reset form fields
        this.showErrorMessage = true
        this.name = ''
        this.password = ''
      }
    },
    goToSignUp () {
      this.$router.push('/signup')
    }
  }
}
</script>

<style scoped>
.login-page {
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, beige, white);
}
.logo-container {
  position: absolute;
  top: 10px;
  left:10px;
}
.login-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 400px;
  height: 400px;
  border-radius: 10px;
  background-color: white;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.1);
  transition: opacity 1.0s ease;
}

h2 {
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  text-align: left;
  display: block;
  margin-bottom: 5px;
}

input[type="text"],
input[type="password"] {
  width: 250px;
  padding: 10px;
  border-radius: 10px;
}
button {
  padding: 10px 20px;
  background-color: beige;
  color: black;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}
button:hover {
  background-color: dimgray;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.1);
  transition: opacity 1.0s ease;
}
.forgot-password-link {
  margin-top: 10px;
}

.forgot-password-link a {
  color: #007bff;
  text-decoration: none;
}

.forgot-password-link a:hover {
  text-decoration: underline;
}
.social-icons{
display: flex;
justify-content: center;
margin-top: 20px;
}
.social-icons .icon{
margin:0 20px;
}
.no-account{
position: absolute;
bottom: 10px;
left: 47.25%;
/* transform: translateX(100%); */
transform: translateY(-270%);
text-align: center;
cursor: pointer;
}
</style>
