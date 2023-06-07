<template>
  <div class="portfolio">

    <main>
      <section class="illustrations">
        <div class="content-showcase-wrapper">
        <div class="content-showcase">           
        <p>Illustrations</p>
      </div></div>
        <div class="illustration-grid">
          <div v-for="(illustration, index) in illustrations" :key="index" class="illustration-card">
            <img :src="illustration.image" alt="Illustration" />
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

    return {
      illustrations,
    };
  },
};
</script>

<style scoped>

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
  grid-template-columns: 1fr 1fr 1fr;
  width: 1080px;
   margin: auto;
  gap: 1rem;
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
</style>
