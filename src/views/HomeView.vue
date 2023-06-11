<template>
    <div class="home">
      <PageLogbar/>
      <div class="home animate">
      <h1>Welcome to My Saenghwal, 안녕! This is My Portfolio Page</h1>
      <!-- <div class="profile-container">
        <div class="profile-picture" @click="togglePicture">
          <img src="../assets/MyPicture.jpg" alt="Profile Picture">
        </div>
        <div v-if="showFullPicture" class="full-picture-overlay" @click="closePicture">
          <div class="full-picture">
            <img src="../assets/MyPicture.jpg" alt="Full Picture">
            <span class="close-icon" @click="closePicture">X</span>
          </div>
        </div>
      </div> -->
      <div class="search-field">
        <input type="text" v-model="searchQuery" placeholder="Search">
        <button @click="search">Search</button>
      </div>
      <div v-if="showErrorMessage" class="error-message">
        Please enter a valid search query.
      </div>
    <div class="main-page-content">
        <div class="section" @click="goToHome()">
        <h2>Home</h2>
        <ul>
          <li>Logo</li>
          <li>Homepage</li>
          <li>About</li>
          <li>Sign In</li>
          <li>Sign Up</li>
          <li>Picture</li>
          <li>Video</li>
          <li>Navigation Menu</li>
        </ul>
      </div>
      <div class="section" @click="goToAbout()">
        <h2>Creators</h2>
        <ul>
          <li>Logo</li>
          <li>Profile</li>
          <li>Gallery</li>
          <li>Academic</li>
          <li>Social Media Platform Interworking (icon)</li>
          <li>Resume (pdf)</li>
          <li>Self-Photo</li>
          <li>Contact</li>
          <li>Self Information</li>
        </ul>
      </div>
      <div class="section" @click="goToSignIn()">
        <h2>Log In</h2>
        <ul>
          <li>Name</li>
          <li>E-mail</li>
          <li>Password (icon)</li>
          <li>Call to Action (CTA) "Forgot Your Password?"</li>
          <li>Headline "안녕 친구/Hello Friend!"</li>
          <li>Sign Up</li>
          <li>Sign In</li>
          <li>Interface Icon (Facebook, Gmail, LinkedIn)</li>
        </ul>
      </div>
      <div class="section" @click="goToSignUp()">
        <h2>Sign Up</h2>
        <ul>
          <li>Name</li>
          <li>E-mail</li>
          <li>Password (icon)</li>
          <li>Interface Icon (Facebook, Gmail, LinkedIn)</li>
          <li>Headline "안녕 친구/Hello Friend!"</li>
          <li>Sign In</li>
          <li>Sign Up</li>
        </ul>
      </div>
      <div class="section" @click="goToAcademic()">
        <h2>Academic</h2>
        <ul>
          <li>Hamburger Menu (About, Academic, Calendar, Profile)</li>
          <li>Log Out</li>
          <li>Picture</li>
          <li>Courses</li>
          <li>Homework</li>
          <li>Announcement</li>
          <li>Text (ID, Department, Name)</li>
        </ul>
      </div>
      <div class="section" @click="goToGallery()">
        <h2>Gallery</h2>
        <ul>
          <li>Log Out</li>
          <li>Academic</li>
          <li>Profile</li>
          <li>Plus Sign/Menu (to upload photos or video)</li>
          <li>Layout of the photos/videos (5x5 or 4x4 or 3x3)</li>
        </ul>
      </div>
  </div>
      <PageFooter/>
    </div>
    </div>
</template>

<script>
import PageFooter from '@/components/PageFooter.vue'
import PageLogbar from '@/components/PageLogbar.vue'

export default {
  name: 'HomeView',
  components: {
    PageFooter,
    PageLogbar
  },
  data () {
    return {
      profilePicture: '../assets/MyPicture.jpg',
      showFullPicture: false,
      searchQuery: '',
      showErrorMessage: false
    }
  },
  methods: {
    togglePicture () {
      this.showFullPicture = !this.showFullPicture
    },
    closePicture () {
      this.showFullPicture = false
    },
    search () {
      if (this.searchQuery.toLowerCase() === 'home') {
        this.$router.push('/')
      } else if (this.searchQuery.toLowerCase() === 'about') {
        this.$router.push('/about')
      } else if (this.searchQuery.toLowerCase() === 'logout') {
        this.$router.push('/logout')
      } else if (this.searchQuery.toLowerCase() === 'login') {
        this.$router.push('/login')
      } else if (this.searchQuery.toLowerCase() === 'academic') {
        this.$router.push('/academic')
      } else if (this.searchQuery.toLowerCase() === 'gallery') {
        this.$router.push('/gallery')
      } else {
        this.showErrorMessage = true
        this.searchQuery = ''
      }
    },
    goToHome () {
      this.$router.push('/')
    },
    goToAbout () {
      this.$router.push('/about')
    },
    goToSignIn () {
      this.$router.push('/login')
    },
    goToSignUp () {
      this.$router.push('/logout')
    },
    goToAcademic () {
      this.$router.push('/academic')
    },
    goToGallery () {
      this.$router.push('/gallery')
    }
  }
}
</script>

<style scoped>
.app-container {
  background: white;
}
.animate{
  opacity: 0;
  transform: translate(-100px);
  animation: slideIn 1s forwards;
}

@keyframes slideIn {
  0% {
    opacity: 0;
    transform: translateY(-100px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.profile-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh; /* Adjust the height as per your layout */
}
h1{
  margin-top: 20px;
  text-align: center;
  font-size: 40px;
}
.profile-picture {
  width: 250px; /* Adjust the width and height as per your requirements */
  height: 250px;
  border-radius: 50%; /* Make it a circle using border-radius */
  overflow: hidden; /* Hide any content that exceeds the circular shape */
  cursor: pointer;
}
.profile-picture img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Maintain the aspect ratio of the image */
}
.full-picture-overlay{
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
  cursor: pointer;
}
.full-picture{
  position: relative;
  max-width: 90%;
  max-height: 90%;
}
.full-picture img {
  max-width: 100%;
  max-height: 100%;
  display: block;
  margin: 0 auto;
}
.close-icon {
  position:fixed;
  top: 20px;
  right: 20px;
  font-size: 24px;
  color: #fff;
  cursor: pointer;
}
.search-field {
  margin-top: 80px; /* Adjust the spacing as needed */
  display: flex;
  align-items: center;
  justify-content: center;
  height: 10vh; /* Adjust the height as per your layout */
}
.search-field input[type="text"] {
  padding: 15px;
  margin-right: 10px; /* Adjust the spacing as needed */
  border-radius: 10px;
  font-size: 16px;
}
.search-field button{
  padding: 5px;
  border-radius: 10px;
  cursor: pointer;
}
.error-message {
  color: red;
  margin-top: 10px;
}
.main-page-content{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.section {
  border-radius: 20px;
  margin: 20px;
  padding: 20px;
  background-color: ivory;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: opacity 1.0s ease;
}
.section:hover{
  cursor: pointer;
  opacity: 0.8;
  background-color: beige;
}
.main-page-content {
  display: grid;
  padding-top: 10px;
  padding: 130px;
  grid-template-columns: repeat(2, minmax(150px, 1fr)); /* Creates 3 equal columns */
  text-align: left;
}
</style>
