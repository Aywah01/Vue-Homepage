<template>
    <div class="logo" @click="goToHome">
        <img alt="Vue logo" src="../assets/MY2.png">
    </div>
  </template>

<script>
export default {
  methods: {
    goToHome () {
      this.$router.push('/')
    }
  }
}
</script>

  <style scoped>
.logo {
    position: absolute;
    top: 20;
    left: 10;
    width: 20px;
    height: 20px;
}
.logo img{
    cursor: pointer;
}
  </style>
