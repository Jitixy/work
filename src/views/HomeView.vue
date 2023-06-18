<template>
  <div class="home">
    <div class="navbar">
      <div class="logo">
        <img src="../assets/logo.png" alt="Logo" />

      </div>
      <nav>
        <router-link to="/history">01.History</router-link>
        <router-link to="/about">02.Team</router-link>
      </nav>
    </div>
    <HelloWorld/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
.home {
  background-image: url("/Users/jiti/Documents/projectwork/src/assets/hi.jpg");
  display: grid;
  min-height: 101vh;
  grid-template-rows: auto 1fr; /* Adjust grid layout to have auto row for navbar and 1fr row for content */
  margin-top: -10px;
  margin-bottom: -1px;
  margin-left: -10px;
  width: 1473px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  grid-row: 1; /* Position navbar in the first row of the grid */
}

.logo {
  margin-left: 350px;
}

.logo img {
  width: 50px; /* Set the width of the logo image */
  height: auto; /* Maintain the aspect ratio of the logo image */
}

nav {
  padding: 10px;
  display: flex; /* Set nav as flex container */
  align-items: center; /* Align items vertically within the nav container */
}

nav a {
  font-weight: bold;
  padding-left: 100px;
  color: #2c3e50;
  margin-left: 10px;
  margin-right: 50px;
  text-decoration: underline; /* Remove underline from links */
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
