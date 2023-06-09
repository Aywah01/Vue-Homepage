<template>
  <div class="nav-bar">
    <router-link class="menu-item" to="/">Home</router-link>
    <router-link class="menu-item" to="/about">About</router-link>
    <router-link class="menu-item" to="/academic">Academic</router-link>
    <router-link class="menu-item" to="/gallery">Gallery</router-link>
    <router-link class="menu-item" to="/login">Log In</router-link>
    <router-link class="menu-item" to="/logout">Log Out</router-link>
    <router-link class="menu-item" to="/signup">Sign Up</router-link>
  </div>
</template>
<style>
.nav-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: beige;
  padding: 10px;
  margin-left: 10px;
}

.menu-item {
  margin: 0 10px;
  text-decoration: none;
  color: #333;
  font-weight: bold;
  padding: 8px 16px;
  border-radius: 4px;
  background-color: #fff;
}

.nav-bar router-link {
  border-radius: 5px;
  margin: 0 10px;
  text-decoration: none;
  color: #333;
  font-weight: bold;
}

.nav-bar router-link:hover {
  color:gray;
  background-color: #e3e3e3;
}
</style>
