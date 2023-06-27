<template>
  <div class="portfolio">
    <main>
      <section class="illustrations">
        <div class="content-showcase-wrapper">
          <div class="content-showcase">
            <p>Illustrations</p>
          </div>
        </div>
        <div class="illustration-grid">
          <div v-for="(illustration, index) in illustrations" :key="index" class="illustration-card">
            <img :src="illustration.image" alt="Illustration" @click="showOverlay(index)" />
          </div>
        </div>
        <div v-if="showOverlayFlag" class="overlay" @click="hideOverlay">
          <div class="overlay-content">
            <span class="close-button" @click="hideOverlay">&times;</span>
            <img :src="illustrations[currentIndex].image" alt="Illustration" />
          </div>
        </div>
      </section>
    </main>
  </div>
</template>


<script>
import { ref } from 'vue';

export default {
  name: 'Portfolio',
  setup() {
    const illustrations = ref([
      { image: 'https://raw.githubusercontent.com/C-junior/khaos-art-portfolio/master/src/assets/nemesis.jpg' },
      { image: 'https://raw.githubusercontent.com/C-junior/khaos-art-portfolio/master/src/assets/nijinrework.png' },
      { image: 'https://raw.githubusercontent.com/C-junior/khaos-art-portfolio/master/src/assets/misty.jpeg' },
      { image: 'https://raw.githubusercontent.com/C-junior/khaos-art-portfolio/master/src/assets/yelanrework.png' },
    
      // Add more illustrations as needed
    ]);

    const showOverlayFlag = ref(false);
    const currentIndex = ref(0);

    const showOverlay = (index) => {
      currentIndex.value = index;
      showOverlayFlag.value = !showOverlayFlag.value; // Toggle the value of showOverlayFlag
    };

    const hideOverlay = () => {
      showOverlayFlag.value = false;
    };

    return {
      illustrations,
      showOverlayFlag,
      currentIndex,
      showOverlay,
      hideOverlay,
    };
  },
};
</script>


<style scoped>

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
}

.overlay-content {
  position: relative;
}

.close-button {
  position: absolute;
  top: 40px;
  left: 40px;
  font-size:60px;
  color: #fff;
  cursor: pointer;
  z-index: 9998;
}

.overlay-content img {
  max-height: 94vh;
}

.content-showcase{
  position: relative;
  padding-bottom: 0;
  top: -87px;
  background: rgb(29, 29, 29);
  width: 20rem;
  margin: auto;
  border-radius: 12px  12px 0 0;
  z-index: 2;
  border: #801010 solid 2px;
  border-bottom: transparent solid 2px
}
.portfolio {
  font-family: Arial, sans-serif;
  color: #801010;
  position: relative;
  top: 0;
}

header {
  background-color: rgb(167, 23, 23);
  padding: 1rem;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: flex-end;
}

nav ul li {
  margin-left: 1rem;
}

nav ul li a {
  color: #fff;
  text-decoration: none;
  transition: color 0.3s ease;
}

nav ul li a:hover {
  color: #ff4081;
}

main {
  padding: 2rem;
  width: 100vw;
  margin: auto;
  background: rgb(29, 29, 29);
  border-top:solid #801010 2px;
}

.illustrations {
  text-align: center;
 
}

.illustrations p {
  font-family: 'Cinzel Decorative', cursive;
  font-size: 2rem;
  
}

.illustration-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  width: 100%;
  gap: 2rem;
  z-index: 0;
}

.illustration-card {
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 0px 2px 5px rgba(105, 4, 4, 0.548);
  transition: transform 0.3s ease;
}

.illustration-card img {
  width: 100%;
  height: auto;
}

.illustration-card:hover {
  transform: translateY(-5px);
  box-shadow: 0px 5px 10px rgba(170, 4, 4, 0.555);
}

@media (max-width: 768px) {
  .illustration-grid {
    grid-template-columns: repeat(auto-fit, minmax(1fr));
  }

  .overlay-content img {
    max-width: 90%;
    max-height: 90%;
  }
  .close-button {
    top:-10px;
    left:10px
  }
}
</style>
