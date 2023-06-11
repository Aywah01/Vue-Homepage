<template>
    <div class="page-header">
      <div class="log-bar">
        <router-link class="menu-item" to="/login">Log In</router-link>
        <router-link class="menu-item" to="/signup">Sign Up</router-link>
      </div>
    </div>
  </template>

  <style>
  /* .page-header {
    position: relative;
  } */

  .page-header{
    /* position: relative; */
    padding: 10px;
  }
  .log-bar {
  display:flex;
  justify-content: center;
  align-items: center;
  /* background-color: beige; */
  padding: 10px;
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

.log-bar router-link {
  border-radius: 5px;
  margin: 0 10px;
  text-decoration: none;
  color: #333;
  font-weight: bold;
}

.log-bar router-link:hover {
  color: gray;
  background-color: #e3e3e3;
}
  </style>
