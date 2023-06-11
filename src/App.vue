<template>
  <div class="app-page">
    <div id="app">
    <PageLogo/>
      <PageHeader/>
    <div class="container">
      <PageMenu/>
    </div>
    <router-view/>
    <PageHamburgerMenu/>
    <div>
  </div>
  </div>
  </div>

</template>
<script>
// import PageHeader from '@/components/PageHeader.vue'
import PageHamburgerMenu from '@/components/PageHamburgerMenu.vue'
import PageLogo from '@/components/PageLogo.vue'
import PageHeader from './components/PageHeader.vue'

export default {
  name: 'app',
  components: {
    PageLogo,
    PageHeader,
    PageHamburgerMenu
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  height: 100vh;
  background: linear-gradient(to bottom, beige, white);
}
.container{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}
.container > * {
  margin-bottom: 10px;
}

.router-view {
  flex-grow: 1;
}

.app-page {
  /* background: beige; */
  border-radius: 10px;
  background: linear-gradient(to bottom, beige, white);
}
</style>
