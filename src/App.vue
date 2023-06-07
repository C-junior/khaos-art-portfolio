
<template>
  <header>
    <div class="header-wrapper">
     
      <div class="header-content">
        <div class="top-divider"></div>
        <nav>
          <RouterLink to="/">Home</RouterLink>
        </nav>
        <img class="h-logo" src="../src/assets/header-logo.svg" alt="">
        
        <nav>
          <RouterLink to="/about">About</RouterLink>
        </nav>
      </div>
    </div>
  </header>

  <img class="mainImg" src="../src/assets/nemesis-nobg.png" alt="">

  <div class="sideDiv">
    <h1>
      Khaos Art
    </h1>
    <div class="card">
    <div class="card-content">
      <div class="profile-image">
        <div class="box"></div>
        <img src="../src/assets/IA art perfil.jpg" />
      </div>
      <p>Follow me on social media:</p>
      <div class="social-links">
        <a href="#" class="social-link facebook">
          <i class="fab fa-facebook"></i> 
        </a>
        <a href="#" class="social-link twitter">
          <i class="fab fa-twitter"></i>
          
        </a>
        <a href="#" class="social-link instagram">
          <i class="fab fa-instagram"></i>
      
        </a>
      </div>
    </div>
  </div>
  </div>

  <div class="conteudo">
    <RouterView />
  </div>

</template>

<style scoped>
.h-logo{
  width: 400px;
}
.box {
  position: absolute;
  left: 110px;
  top: 122px;
  width: 130px;
  height: 130px;
  border-radius: 50%;
  background: linear-gradient(45deg, transparent, transparent 40%, rgb(255, 0, 0)),
    linear-gradient(#262626, #141414);
  animation: rotate 1.5s linear infinite;
  z-index: -1;
}

.box:before,
.box:after {
  content: " ";
  position: absolute;
  inset: 8px;
  background: linear-gradient(#161616, #262626);
  border-radius: inherit;
}

.box:before {
  background: linear-gradient(45deg, transparent, transparent 40%, rgb(255, 0, 0));
  filter: blur(32px);
}

@keyframes rotate {
  100% {
    transform: rotate(360deg);
  }
}


.card {
  border-radius: 8px;
  margin: auto;
  width: 300px;
  padding: 20px;
  color: #fff;
}
.card-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.profile-image {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background-color: #fff;
  margin-bottom: 20px;
  /* Add animations or transitions here */
}

h2 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

p {
  margin-bottom: 20px;
}

.social-links {
  display: flex;
  justify-content: center;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #000;
  color: #fff;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 0 10px;
  transition: background-color 0.3s ease;
  position: relative;
}

.social-link:hover {
  background-color: #ff1e00;
}

.social-link:before {
  content: "";
  position: absolute;
  top: -5px;
  left: -5px;
  right: -5px;
  bottom: -5px;
  border-radius: 50%;
  background-color: #00ccff;
  z-index: -1;
  opacity: 0.4;
  filter: blur(8px);
}

.facebook {
  background-color: #3b5998;
}

.twitter {
  background-color: #1da1f2;
}

.instagram {
  background-color: #c13584;
}

.social-link i {
  font-size: 20px;
}

.social-link i.fa-facebook-f {
  /* Customize styles for Facebook link */
  color: #3b5998;
}

.social-link i.fa-twitter {
  /* Customize styles for Twitter link */
  color: #1da1f2;
}

.social-link i.fa-instagram {
  /* Customize styles for Instagram link */
  color: #c13584;
}
.profile-image img {
width: 100%;
height: 100%;
border-radius: 50%;
z-index: 99;
}


.header-wrapper {
  width: 100vw;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  z-index: 2;
}
.top-divider{
  width: 100%;
  height: 1rem;
  background-color: #801010;
  position: absolute;
  left: 0;
  top: 0;
}
.header-content {
  display: flex;
  align-items: center;  
}

.name {
  text-align: center;
  font-family: 'Cinzel Decorative', cursive;
  padding: 0 4rem;
  color: rgb(19, 19, 19);
  background-color: red;
}

header {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-height: 84px;
  background-color: #1f1f1f;
}

.mainImg {
  width: 100vw;
  position: relative;
  top: -80px;
  left: -500px;
  z-index: 1;
}

.logo {
  display: block;
  margin: 0;
  position: relative;
  left: 0;
}

nav {
  display: flex;
  justify-content: center;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: none;
}

.conteudo {
  position: absolute;
  top: 800px;
  background-color: #1f1f1f;
  z-index: 3;
}

.sideDiv {
  position: absolute;
  top: 200px;
  right: 0;
  background-color: #1f1f1f;
  height: 500px;
  width: 350px;
  z-index: 12;
}

.sideDiv h1 {
  font-family: 'Cinzel Decorative', cursive;
  text-align: center;
  padding-top: 60px;
  color: #be1515;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: start;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
