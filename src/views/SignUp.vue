<template>
    <div class="signup-page">
      <div class="logo-container">
        <PageLogo/>
      </div>
        <div class="signup-container">
            <h2>Create Account</h2>
            <form @submit="signup">
            <div class="form-group">
                <label for="name">Create Username</label>
                <input type="text" id="name" v-model="name" required placeholder="Create a New Username">
            </div>
            <div class="form-group">
                <label for="email">Your E-mail</label>
                <input type="email" id="email" v-model="email" required placeholder="Enter a Valid Email">
            </div>
            <div class="form-group">
                <label for="password">Create Password</label>
                <input type="password" id="password" v-model="password" required placeholder="Create a New Password">
            </div>
            <label class="terms"><input type="radio" id="termsRadioButton" v-model="agreeTerms">
                I agree to The Terms & Conditions
            </label>
            <button type="submit" @click="signUp" :disabled="!agreeTerms">Get Started</button>
            </form>
            <div class="social-icons">
                <a href="#" class="icon"><i class="fab fa-google fa-3x"></i></a>
                <a href="#" class="icon"><i class="fab fa-facebook fa-3x"></i></a>
                <a href="#" class="icon"><i class="fab fa-linkedin fa-3x"></i></a>
            </div>
        </div>
        <div class="got-account" @click="goToSignIn">
            <p>Already Have an Account?</p>
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
      name: '',
      email: '',
      password: '',
      agreeTerms: false
    }
  },
  methods: {
    signup (event) {
      event.preventDefault()
      console.log('Create Username', this.name)
      console.log('Your E-mail', this.email)
      console.log('Create Password', this.password)
      this.name = ''
      this.email = ''
      this.password = ''
      this.$router.push('/login')
    },
    signUp () {
      if (this.agreeTerms) {
        console.log('Sign Up Successful')
      }
    },
    goToSignIn () {
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>
.signup-page {
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
/* background-color: beige; */
background: linear-gradient(to bottom, beige, white);
}
.logo-container {
  position: absolute;
  top: 10px;
  left:10px;
}
.signup-container {
display: flex;
flex-direction: column;
align-items: center;
width: 500px;
height: 500px;
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
font-size: medium;
text-align: left;
display: block;
margin-bottom: 10px;
margin-top: 10px;
}

.terms{
display: block;
margin-bottom: 10px;
margin-top: 10px;
}

input[type="text"],
input[type="email"],
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
.social-icons{
display: flex;
justify-content: center;
margin-top: 20px;
}
.social-icons .icon{
margin:0 20px;
}

.got-account{
position: absolute;
bottom: 10px;
left: 54%;
/* transform: translateX(100%); */
transform: translateY(-170%);
text-align: center;
cursor: pointer;
}
</style>
