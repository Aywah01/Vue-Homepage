<template>
  <div :class="['sidebar-menu', { 'open': isMenuOpen }]">
    <div class="hamburger" @click="toggleMenu">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <ul v-show="isMenuOpen" class="menu-items">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/academic">Academic</router-link></li>
        <li><router-link to="/Gallery">Gallery</router-link></li>
        <li><router-link to="/login">Log In</router-link></li>
        <li><router-link to="/signup">Sign Up</router-link></li>
        <li><router-link to="/logout">Log Out</router-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu () {
      this.isMenuOpen = !this.isMenuOpen
    }
  }
}
</script>

<style scoped>
/* Add your sidebar menu styles here */
.sidebar-menu {
  position: fixed;
  top: 0;
  right: 0;
  width: 150px;
  height: 100vh;
  background: transparent;
  padding: 20px;
  transition: background-color 0.3s ease;
}

.sidebar-menu.open{
  background: beige;
}

.hamburger {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  align-self: flex-end;
}

.hamburger span {
  display: flex;
  top: 20;
  right: 10;
  align-self: flex-end;
  width: 30px;
  height: 3px;
  background: #333;
  margin-bottom: 5px;
}

.menu-items {
  margin-top: 20px;
  list-style: none;
  text-align: left;
  align-items: flex-start;
  padding-right: 0;
}

.menu-items li {
  margin-bottom: 10px;
}
</style>
