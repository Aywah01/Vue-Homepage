<template>
  <div class="nav-bar">
    <router-link class="menu-item" to="/">Home</router-link>
    <router-link class="menu-item" to="/about">Creators</router-link>
    <router-link class="menu-item" to="/academic">Academic</router-link>
    <router-link class="menu-item" to="/gallery">Gallery</router-link>
  </div>
</template>

<style>
.nav-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: beige;
  padding: 10px;
  padding-bottom: 50px;
  margin: 0 auto;
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
  color: gray;
  background-color: #e3e3e3;
}
</style>
