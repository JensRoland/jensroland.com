<script setup lang="ts">
import Sidebar from '@/components/Sidebar.vue'
import CoverStory from '@/components/CoverStory.vue'
import Articles from '@/components/Articles.vue'
</script>

<template>
  <header id="hero-header">
    <h2>Leadership &amp; Technology</h2>
    <img id="portrait-background" src="./assets/portrait-by-stefan-aronsen-transparent.webp" alt="Portrait drawing of Jens Roland">
    <img id="signature" src="./assets/signature.webp" alt="Jens Roland" draggable="false">
  </header>

  <main>
    <CoverStory />
  </main>

  <Articles />

  <Sidebar />
</template>

<style lang="scss">
@import './assets/base.css';

#app {
  margin: 0 auto;
  font-weight: normal;
}

main {
  margin-bottom: 6rem;
}

#hero-header,
main {
  margin-left: 600px;
  margin-right: 2rem;
}

#hero-header {
  text-align: center;
  padding: 3rem 0;
  margin-bottom: 5rem;
}
#hero-header h2 {
  font-family: var(--font-headings-sans);
  font-size: 2.2rem;
  font-weight: 100;
  text-align: center;
  margin-bottom: 6rem;
  letter-spacing: 0.25em;
  opacity: 0.6;
  user-select: none;
}
#hero-header img {
  margin: 0 auto;
}
#hero-header #signature {
  mix-blend-mode: multiply;
  opacity: 0.7;
  max-width: 100%;
}

/* Full desktop experience */
@media only screen and (min-width: 1280px) {
  #hero-header #portrait-background {
    display: none;
  }
}

/* Mobile & Tablet */
@media only screen and (max-width: 1280px) {

  body {
    font-size: 14px;
  }

  #hero-header {
    margin: 0;
  }
  main {
    margin: 0 1rem;
  }

  #hero-header {
    padding: 1rem;
    margin-bottom: 0;
  }
  #hero-header h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }
  #hero-header #portrait-background {
    max-width: 100%;
  }
  #hero-header #signature {
    max-width: 75%;
  }
}

</style>
