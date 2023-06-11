<template>
  <footer>
    <div class="footer-page"><hr>
      <div class="contact-container">
        <div class="logo-footer" @click="scrollToTop">
      <PageLogo/>
        </div>
        <div class="contact">
        <h1>Contact</h1>
      </div>
      <div class="about-us">
        <p><i class="fas fa-envelope"></i> Email: rujhanmunawwaruzzaman@gmail.com</p>
        <p><i class="fas fa-phone"></i> Phone: +821075606191</p>
        <p><i class="fas fa-map-marker-alt"></i> Address: Guro-gu, Seoul, South Korea</p>
      </div>
      </div>
  </div>
  </footer>
</template>

<script>

import PageLogo from './PageLogo.vue'

export default {
  components: {
    PageLogo
  },
  methods: {
    scrollToTop () {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  }
}
</script>

  <style>
  .footer-page {
    background-color: beige;
    padding-bottom: 30px;
    position: relative;
    margin: 10px 0;
  }
  .logo-footer{
    display:block;
    position:static;
    right: 250px;
    top: 50px;
    cursor: pointer;
  }
  .contact-container{
    margin: 0 10px 5px 0px;
    padding-top: 20px;
    padding-bottom: 20px;
  }
  .contact h1 {
  margin-bottom: 10px;
}

.about-us p {
  margin: 20px 0;
}

.about-us p i {
  margin-right: 5px;
}

.fa-envelope,
.fa-phone,
.fa-map-marker-alt {
  color: #333;
}
  </style>
