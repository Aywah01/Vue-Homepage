<template>
  <div class="about">
    <h1>Creators</h1>
    <div class="about-container">
      <div class="creator1">
        <div class="profile-picture1" @click="togglePicture1">
          <img src="../assets/Mypictures.jpg" alt="Profile Picture">
        </div>
        <div class="about-creator">
          <div class="label"><h2>Creator 1</h2></div>
          <li><strong>Name:
          </strong>Rujhan bin Munawwaruzzaman(루즈한)</li><br>
          <li><strong>University:
          </strong> Dongyang Mirae University</li><br>
          <li><strong>Age:
          </strong> 20</li><br>
          <li><strong>Occupation:
          </strong>Full-Stack Developer</li><br>
          <button class="more-button" @click="gotoAcademic">More</button>
        </div>
        <div v-if="showFullPicture1" class="full-picture-overlay" @click="closePicture1">
          <div class="full-picture">
            <img src="../assets/Mypictures.jpg" alt="Full Picture">
            <span class="close-icon" @click="closePicture1">X</span>
          </div>
        </div>
      </div>
      <div class="creator2">
        <div class="profile-picture2" @click="togglePicture2">
          <img src="../assets/Mypicture2.jpg" alt="Profile Picture">
        </div>
        <div class="about-creator">
          <div class="label"><h2>Creator 2</h2></div>
          <li><strong>Name:
          </strong>Sharifah Ilham Sofea binti Nazarudin(소피아)</li><br>
          <li><strong>University:
          </strong>Sungkyunkwan University</li><br>
          <li><strong>Age:
          </strong>21</li><br>
          <li><strong>Occupation:
          </strong>Software Developer</li><br>
          <button class="more-button" @click="gotoAcademic">More</button>
        </div>
        <div v-if="showFullPicture2" class="full-picture-overlay" @click="closePicture2">
          <div class="full-picture">
            <img src="../assets/Mypicture2.jpg" alt="Full Picture">
            <span class="close-icon" @click="closePicture2">X</span>
          </div>
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
    },
    gotoAcademic () {
      this.$router.push('/academic')
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
.creator1, .creator2 {
  width: 500px; /* Adjust the width of the container as per your requirements */
  height: 600px; /* Adjust the height of the container as per your requirements */
  margin: 0 10px; /* Adjust the margin as per your layout */
  display: flex;
  flex-direction: column;
  justify-content: top;
  align-items: center;
  background-color: ivory;
  border-radius: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: opacity 1.0s ease;
}
.about-creator{
  width: 420px; /* Adjust the width of the container as per your requirements */
  height: 300px; /* Adjust the height of the container as per your requirements */
  margin: 20px 20px; /* Adjust the margin as per your layout */
  display: flex;
  flex-direction: column;
  justify-content: top;
  align-items: center;
  background-color: #fff;
  border-radius: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: opacity 1.0s ease;
}
.creator1:hover, .creator2:hover{
  cursor: pointer;
  opacity: 0.8;
  background-color: beige;
}
h1{
  margin-top: 10px;
  text-align: center;
}
.more-button{
  padding: 10px;
  border-radius: 5px;
  background: beige;
  cursor: pointer;
}
.profile-picture1 {
  position: relative;
  width: 250px; /* Adjust the width and height as per your requirements */
  height: 250px;
  border-radius: 50%; /* Make it a circle using border-radius */
  overflow: hidden; /* Hide any content that exceeds the circular shape */
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 10px;
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
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 10px;
}
.profile-picture2 img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Maintain the aspect ratio of the image */
}
.label {
  text-align: center;
  font-size: 14px;
  color: #333;
  margin-top: 20px; /* Adjust the margin as per your preference */
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
