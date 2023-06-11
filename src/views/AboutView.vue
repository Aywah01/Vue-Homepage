<template>
  <div class="about">
    <h1>Creators</h1>
    <div class="about-container">
      <div class="profile-picture1" @click="togglePicture1">
          <img src="../assets/Mypictures.jpg" alt="Profile Picture">
          <div class="label">Creator 1</div>
        </div>
        <div v-if="showFullPicture1" class="full-picture-overlay" @click="closePicture1">
          <div class="full-picture">
            <img src="../assets/Mypictures.jpg" alt="Full Picture">
            <span class="close-icon" @click="closePicture1">X</span>
          </div>
        </div>
        <div class="profile-picture2" @click="togglePicture2">
          <img src="../assets/Mypicture2.jpg" alt="Profile Picture">
          <div class="label">Creator 2</div>
        </div>
        <div v-if="showFullPicture2" class="full-picture-overlay" @click="closePicture2">
          <div class="full-picture">
            <img src="../assets/Mypicture2.jpg" alt="Full Picture">
            <span class="close-icon" @click="closePicture2">X</span>
          </div>
        </div>
    </div>
  </div>
</template>
<script>

export default {
  data () {
    return {
      profilePicture1: '../assets/Mypictures.jpg',
      profilePicture2: '../assets/Mypicture2.jpg',
      showFullPicture1: false,
      showFullPicture2: false,
      searchQuery: '',
      showErrorMessage: false
    }
  },
  methods: {
    togglePicture1 () {
      this.showFullPicture1 = !this.showFullPicture1
    },
    closePicture1 () {
      this.showFullPicture1 = false
    },
    togglePicture2 () {
      this.showFullPicture2 = !this.showFullPicture2
    },
    closePicture2 () {
      this.showFullPicture2 = false
    }
  }
}
</script>
<style>
.about-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: auto;
  height: 100vh; /* Adjust the height as per your layout */
}
h1{
  margin-top: 10px;
  text-align: center;
}
.profile-picture1 {
  position: relative;
  width: 250px; /* Adjust the width and height as per your requirements */
  height: 250px;
  border-radius: 50%; /* Make it a circle using border-radius */
  overflow: hidden; /* Hide any content that exceeds the circular shape */
  cursor: pointer;
}
.profile-picture1 img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Maintain the aspect ratio of the image */
}
.profile-picture2 {
  position: relative;
  width: 250px; /* Adjust the width and height as per your requirements */
  height: 250px;
  border-radius: 50%; /* Make it a circle using border-radius */
  overflow: hidden; /* Hide any content that exceeds the circular shape */
  cursor: pointer;
  margin-left: 20px;
}
.profile-picture2 img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Maintain the aspect ratio of the image */
}
.label {
  position: absolute;
  bottom: -20px; /* Adjust the distance from the picture */
  left: 0;
  width: 100%;
  text-align: center;
  font-size: 14px;
  color: #333;
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
</style>
