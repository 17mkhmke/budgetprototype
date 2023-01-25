<template>
  <NavBar/>
  
  <router-view/>

  <Footer/>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import Footer from '@/components/Footer.vue'

export default{
  components: {
    NavBar,
    Footer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  min-height: 100vh;
  /* border: 2px solid yellow; */

  background-image: linear-gradient(#c4c4c4,#ff9001);
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  transition: all 0.5s ease 0s;
}

nav a.router-link-exact-active {
  color: #ff9001;
}



</style>
