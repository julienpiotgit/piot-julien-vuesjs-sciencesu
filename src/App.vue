<template>
  <div id="app">
    <NavBar />

    <router-view />

    <Footer />
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
  </div>
</template>

<script>
import NavBar from '@/views/NavBar.vue'
import Footer from '@/views/Footer.vue'

export default {
  name: 'Home',
  components: {
    NavBar,
    Footer
  }
}
</script>
