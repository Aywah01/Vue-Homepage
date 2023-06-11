<template>
  <div class="gallery-page">
    <h1>My Gallery</h1>
    <h2>MT 2023</h2><button @click="toggleGridLayout">3x3 or 4x4</button>
    <div class="gallery-container" :class="gridLayoutClass">
      <img src="../assets/image0.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image1.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image2.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image3.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image4.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image5.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image6.png" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image7.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image8.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image9.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image10.jpg" alt="Profile Picture" class="tilted-images">
      <img src="../assets/image11.jpg" alt="Profile Picture" class="tilted-images">
    </div>
    <div class="video-container">
      <video src="../assets/MTVlog.mp4" controls></video>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      gridLayout: '3x3'
    }
  },
  computed: {
    gridLayoutClass () {
      return `grid-${this.gridLayout}`
    }
  },
  methods: {
    toggleGridLayout () {
      if (this.gridLayout === '3x3') {
        this.gridLayout = '4x4' // Change to 4x4 layout
      } else {
        this.gridLayout = '3x3' // Change back to 3x3 layout
      }
    }
  }
}
</script>

<style>
  .gallery-page {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .gallery-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 30px;
    justify-items: center; /* Center horizontally */
    align-items: center; /* Center vertically */
    margin-top: 20px;
  }
.grid-4x4 {
  grid-template-columns: repeat(4, 1fr);
  }
  button{
    margin-top: 10px;
    padding: 10px;
    background-color: beige;
    border-radius: 10px;
    cursor: pointer;
  }

  .gallery-container img {
    border-radius: 20px;
    width: 300px;
    height: auto;
    transition: transform 0.3s ease;
  }

  .gallery-container img:hover {
    transform: rotate(-5deg);
  }

  .video-container {
    padding : 20px;
    max-width: 600px; /* Adjust the width as needed */
    margin: 0 auto;
    border-radius: 70px; /* Add border radius */
    overflow: hidden; /* Clip the video within the container */
  }

  .video-container video {
    width: 100%;
    height: auto;
  }
</style>
