<template>
    <div class="home">
      <div class="navbar">
        <div class="logo">
          <img src="../assets/logo1.png" alt="Logo" />
        </div>
        <nav>
          <router-link to="/history">01.History</router-link>
          <router-link to="/about">02.Team</router-link>
        </nav>
      </div>
      <div class="body">
        <div class="bg">
          <div class="text-5">
            <div class="wrapper-2">
              <p class="history">HISTORY</p>
              <p class="text-6">01.</p>
            </div>
            <p class="text-7">
             Hello,welcome to this project made by Daljeet Singh.Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptates ratione, impedit ullam facilis voluptatem minus laborum vitae blanditiis laboriosam Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima mollitia modi expedita tenetur unde deleniti alias praesentium. Dolorum ipsa tenetur quibusdam repudiandae deleniti. Sed harum porro dicta, mollitia ducimus sequi.
            </p>
          </div>
        </div>
        <div class="bg-2">
          <div class="image-2"></div>
          <div class="thumbnails group">
            <img
              v-for="(image, index) in images"
              :key="index"
              :src="image.src"
              :alt="image.alt"
              @click="openModal(index)"
              :class="{ 'highlighted': highlightedIndex === index }"
            >
          </div>
          <div class="circle-nav group">
            <div
              v-for="(image, index) in images"
              :key="index"
              class="ellipse-1"
              :class="{ 'active': highlightedIndex === index }"
              @click="highlightImage(index)"
            ></div>
          </div>
        </div>
      </div>
      <div v-if="selectedImage" class="modal">
        <div class="modal-content">
          <button class="modal-close" @click="closeModal">&times;</button> <!-- Added cross button -->
          <img :src="selectedImage.src" :alt="selectedImage.alt" />
          <button class="modal-prev" @click="navigateImage(-1)">&#8249;</button>
          <button class="modal-next" @click="navigateImage(1)">&#8250;</button>
        </div>
      </div>
    </div>
  </template>

  <style scoped>
  /* Your existing styles */
  
  .thumbnails {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 11px;
  
  }
  
  .thumbnails img {
    width: 14%;
    height: 100%;
    object-fit: cover;
    margin: 30px 10px;
    cursor: pointer;
    opacity: 0.7;
    transition: opacity 0.3s ease;
  }
  
  .thumbnails img.highlighted {
    opacity: 1;
    border: 10px solid black;
  }
  
  .circle-nav {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 10px;
  }
  
  .circle-nav .ellipse-1 {
    width: 10px;
    height: 10px;
    background-color: #bbb;
    border-radius: 50%;
    margin: 0 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .circle-nav .ellipse-1.active {
    background-color: #333;
  }
  </style>
  
  <script>
export default {
  data() {
    return {
      images: [
        { src: require('../assets/rectangle_23_copy.jpg'), alt: 'Image 1' },
        { src: require('../assets/rectangle_23.jpg'), alt: 'Image 2' },
        { src: require('../assets/rectangle_23_copy.jpg'), alt: 'Image 3' },
        { src: require('../assets/rectangle_23.jpg'), alt: 'Image 4' },
      ],
      selectedImage: null,
      highlightedIndex: 0,
    };
  },
  methods: {
    highlightImage(index) {
      this.highlightedIndex = index;
    },
    openModal(index) {
      this.selectedImage = this.images[index];
    },
    closeModal() {
      this.selectedImage = null;
    },
    navigateImage(direction) {
      const currentIndex = this.images.indexOf(this.selectedImage);
      const newIndex = (currentIndex + direction + this.images.length) % this.images.length;
      this.selectedImage = this.images[newIndex];
    },
  },
};
</script>
  
  <style scoped>


.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: -10px;
  grid-row: 1;
  background-color: white; /* Position navbar in the first row of the grid */
}

.logo {
  margin-left: 350px;
}

.logo img {
  width: 200px; /* Set the width of the logo image */
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
.bg {
    margin: 14px auto 0;
    padding: 44px 0 453px;
    position: relative;
    width: 100%; /* 1600px / 1600px = 100% */
    background: url(../assets/peak_2.jpg) no-repeat center 0;
    background-position: center top;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
  }
  .bg-2 {
    height: 195px;
    margin: -20px auto;
    position: relative;
    width: 100%; /* 1600px / 1600px = 100% */
    background: #414f6b;
  }
  .circle-nav {
    left: 50%;
    position: absolute;
    top: 171px;
    width: 30px;
    margin-left: -15px;
  }
  .circle-nav > * {
    float: left;
    margin: 0 6px 0 0;
  }
  .circle-nav > *:last-child {
    margin-right: 0 !important;
  }
  .text-5 {
    margin: 0 auto;
    position: relative;
    width: 960px;
    z-index: 0;
  }
  .text-6 {
    left: 38%;
    position: absolute;
    top: -78%;
    opacity: 0.5;
    color: #414f6b;
    font-family: Oswald, sans-serif;
    font-size: 8.476721rem; /* 135.63px / 16px = 8.476875rem */
    font-weight: bold;
    line-height: 148px;
    margin-left: -124.5px;
  }
  .text-7 {
    margin: -8px auto 0;
    position: relative;
    width: 813px;
    z-index: 84;
    font-weight: 300;
    line-height: 24px;
  }
  .history {
    left: 50%;
    position: absolute;
    top: 50px;
    color: #414f6b;
    font-family: Oswald, sans-serif;
    font-size: 2rem; /* 32px / 16px = 2rem */
    font-weight: bold;
    line-height: 35px;
    margin-left: 4.5px;
  }
  .wrapper-2 {
  height: 148px;

  position: relative;
  width: 249px;
  z-index: 85;
}
.image-2 {
    height: 195px;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%; /* 1600px / 1600px = 100% */
    background: url(../assets/peak.jpg) no-repeat center 0;
    background-position: center top;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    opacity: 0.2;
  }
  .bg-2{
    position: relative;
    top: 1%;
  }
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }
  
  .modal-content {
    position: relative;
    max-width: 90%;
    max-height: 90%;
  }
  
  .modal img {
    width: 500px;
    height: 400px;
  }
  
  .modal-navigation {
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
  }
  
  .modal-navigation button {
    background-color: transparent;
    border: none;
    color: #fff;
    font-size: 24px;
    cursor: pointer;
  }
  
  .modal-prev {
    position: relative;
    left: -532px;
  }
  
  .modal-next {
    margin-left: auto;
  }
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }

  .modal-content {
    position: relative;
    max-width: 90%;
    max-height: 90%;
  }

  .modal img {
    max-width: 100%;
    max-height: 100%;
  }

  .modal-navigation {
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
  }

  .modal-navigation button {
    background-color: transparent;
    border: none;
    color: #fff;
    font-size: 24px;
    cursor: pointer;
  }

  .modal-prev {
    margin-right: auto;
  }

  .modal-next {
    margin-left: auto;
  }
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }
  
  .modal-content {
    position: relative;
    max-width: 90%;
    max-height: 90%;
  }
  
  .modal img {
    max-width: 100%;
    max-height: 100%;
  }
  
  .modal-navigation {
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
  }
  
  .modal-navigation button {
    background-color: transparent;
    border: none;
    color: #fff;
    font-size: 24px;
    cursor: pointer;
  }
  
  .modal-prev {
    margin-right: auto;
  }
  
  .modal-next {
    margin-left: auto;
  }
  .modal-close {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 24px;
    color: #fff;
    background-color: transparent;
    border: none;
    cursor: pointer;
  }
  .home {
    
    display: grid;
    min-height: 105vh;
    grid-template-rows: auto 1fr; /* Adjust grid layout to have auto row for navbar and 1fr row for content */
    margin-top: -10px;
    margin-bottom: -10px;
    margin-left: -10px;
    width: 1473px;
  }
</style>
