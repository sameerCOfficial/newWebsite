<script setup>
import { ref } from 'vue';
  const rows = ref([
    [
      { title: 'SkinCare.io', imageUrl: '../skincare.png'},
      { title: 'SertGPT', imageUrl: '../sertgpt.png' },
    ],
    [
      { title: 'SERT Social',  imageUrl: '../sertsocial.png' },
      { title: 'Balkan Website',  imageUrl: '../balkan.png' },
    ],
  ]);

  const scrollToElement = (elementId) => {
    const targetElement = document.getElementById(elementId);

    if (targetElement) {
      targetElement.scrollIntoView({
        behavior: 'smooth',
      });
    }
  };
</script>

<template>
  <div class="custom-bg">
    <header>
      <div class="wrapper2">
        <nav class="navbar custom-nav" role="navigation" aria-label="main navigation">
          <div class="navbar-brand">
            <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
              <span aria-hidden="true"></span>
              <span aria-hidden="true"></span>
              <span aria-hidden="true"></span>
            </a>
          </div>
          <div id="navbarBasicExample" class="navbar-menu">
            <div class="navbar-start">
              <a class="navbar-item">
                home
              </a>
              <a class="navbar-item" @click="scrollToElement('about')">
                  about
              </a>
              <a class="navbar-item">
                contact
              </a>
            </div>
          </div>
        </nav>
      </div>
      <div class="wrapper">
        <div class="columns is-centered is-vcentered">
          <div class="column is-one-third" id="profile"> 
            <img src="../assets/sameerpfp.png" alt="Sameer Chawla" width="225" height="225">
          </div>
          <div class="column is-two-thirds" id="centertext"> 
            Sameer <br>Chawla
          </div>
        </div>
        <div class="columns is-centered is-vcentered" id="CVButtons">
          <div class="column is-full">
            <a href="../../public/resume.pdf" download="resume.pdf" class="button is-white" id="button-style-1">
              <img src="../assets/icons8-resume-50.png" alt="Resume">cv
            </a>
            <a href="#" class="button is-white is-clickable" @click="scrollToElement('projects')">projects</a>
          </div>
        </div>
      </div>
    </header>
    <main>
      <section class="section is-medium" id="projects">
        <div class="titles">
          <h1 class="title">projects</h1>
          <h2 class="subtitle">
            some of my recent <strong>websites</strong> and <strong>applications</strong> :-)
          </h2>
        </div>
        <div v-for="(row, rowIndex) in rows" :key="rowIndex" class="tile is-ancestor">
          <div v-for="(tile, tileIndex) in row" :key="tileIndex" class="tile is-parent">
            <div class="tile is-child">
              <article class="notification is-white">
                <p class="title" style="text-align:center">{{ tile.title }}</p>
                <figure class="image is-15by9">
                  <img :src="tile.imageUrl" alt="Project Image">
                </figure>
              </article>
            </div>
          </div>
        </div>
      </section>
      <section class="section is-medium" id="about">
        <div class="titles">
          <h1 class="title">about me</h1>
          <h2 class="subtitle"> a bit about sameer chawla</h2>
        </div>
  <div class="tile is-ancestor">
  <div class="tile is-4 is-vertical is-parent">
    <div class="tile is-child box">
      <p class="title">Skills</p>
      <div class="skills">
       <img src="../assets/vuejs.png">
       <img src="../assets/html.png">
       <img src="../assets/css.png">
       <img src="../assets/js.png">
       <img src="../assets/react.png">
      </div>
      
    </div>
    <div class="tile is-child box">
      <p class="title">Education</p>
      <p>University of Maryland, College Park B.S in Computer Science, 2027</p>
      <p>South River High School, Graduated 2023</p>
    </div>
  </div>
  <div class="tile is-parent">
    <div class="tile is-child box">
      <p class="title">About me!</p>
      <p style="font-size:25px">
        Hello, I'm Sameer! A prospective software engineer and full-stack web developer. My passion lies in creating programs that solve problems.
        Outside of programming I enjoy boxing, going on runs, and solving Rubik's cubes!
      </p>
    </div>
  </div>
</div>
</section>
<section class="section is-medium" id="contact">
  <div class="titles">
  <h1 class="title">contact</h1>
</div>
<div class="contact-buttons">
  <a href="https://github.com/sameerCOfficial">
        <img border="0" style="margin-right:50px" alt="Github" src="../assets/github-mark.png" width="200" height="200">
  </a>
  <a href="https://www.linkedin.com/in/sameer-chawla-078466271/">
        <img border="0" style="margin-left:50px" alt="Github" src="../assets/linkedin.png" width="230" height="230">
  </a>
</div>
</section>
</main>
</div>
</template>

<style scoped>
  @import url('https://fonts.cdnfonts.com/css/broadley');
  #profile {
    animation: fadeInLeft 2.4s;
    width: 80%; 
    max-width: 225px; 
    margin: 0 auto;
    padding: 2% 0; 
    margin-top: -100px;
  }

  .contact-buttons {
    display: flex;
    justify-content: center;
    padding: 10px;
  }
  .wrapper2 {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  #centertext {
    font-family: broadley;
    font-size: 5vw; 
    animation: fadeInTop 2.4s;
    padding: 2% 0; 
    color: white;
    text-align: center; 
    margin-bottom: 100px; 
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center; 
    justify-content: center; 
    min-height: 90vh;
  }
  #CVButtons {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-right:50px;
  }
  .button {
    margin-left: 50px; 
    font-size:2vw;
    font-family:Rubik;
    box-shadow: 4px 6px rgba(0, 0, 0, 0.1); 
  }
  .titles{
    text-align: center;
    padding:80px;
  }
  @media screen and (max-width: 768px) {
    #centertext {
      font-size: 6vw; 
    }
    .button {
      margin-left: 50px; 
      font-size:3.4vw;
    }
    #CVButtons {
      margin-top:-60px;
      margin-left:1.048vw;
    }
    .button img {
      max-width: 30px;
      max-height: 30px;
    }
    .contact-buttons {
      margin-right:20px;
    }
  }
  body {
    scroll-behavior: smooth;
  }
  .is-child{
    box-shadow: 4px 6px rgba(0, 0, 0, 0.1); 
  }

  .skills {
    display: flex;
    flex-direction: row;
    max-height: 50px;
    max-width: 50px;
  }
</style>
