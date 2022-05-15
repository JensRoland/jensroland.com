<script setup lang="ts">

</script>

<template>
  <div class="sidebar">
    <img id="portrait-background" src="../assets/portrait-by-stefan-aronsen-transparent.webp" alt="Portrait drawing of Jens Roland">
    <div class="social-links">
      <a href="https://github.com/JensRoland">
        <span class="github logo" title="Github"></span>
        <p>github</p>
      </a>
      <a href="https://www.linkedin.com/in/jensroland">
        <span class="linkedin logo" title="LinkedIn"></span>
        <p>linkedin</p>
      </a>
      <a href="https://stackoverflow.com/users/57068/jens-roland">
        <span class="stackoverflow logo" title="Stack Overflow"></span>
        <p>stackover&hellip;</p><!-- Thank you, I'll be here all week. -->
      </a>
      <a href="mailto:mail@jensroland.com">
        <span class="email logo" title="Email me"></span>
        <p>email</p>
      </a>
    </div>
    <h2>Hi, I'm Jens!</h2>
    <p>
      I am a platform engineering lead from Denmark, specialized in cloud, big data, analytics, and machine learning.
    </p>
    <p>
      This is my personal web site where I <strike>generously</strike> <strike>pompously</strike> unapologetically share my thoughts and experiences on leadership, technology, innovation, and &mdash; sometimes &mdash; woodworking.
    </p>
    <p>
      I currently work at a <a href="https://zeronorth.com/" title="ZeroNorth">company you haven’t heard of</a>, helping to solve <a href="https://www.un.org/press/en/2021/sc14445.doc.htm" title="Hint: It's climate change"><i>the biggest threat modern humans have ever faced</i></a>.
    </p>
    <!-- <p>
      Previously, I have worked on platforms which:
    </p>
    <ul>
        <li class="logo-rayintelligence">Made <a href="https://www.raysearchlabs.com/">cancer treatments more effective</a> through analytics and machine learning</li>
        <li class="logo-audienceproject"><a href="https://www.audienceproject.com/">Reduced the number of banner ads online</a>, and is now used internally by both Google and Facebook to validate and improve their ad targeting algorithms</li>
        <li class="logo-electrolux">Helped sell more <a href="https://www.electrolux.com/">dishwashers and vacuum cleaners</a></li>
    </ul> -->
    <p>
      When I'm not fighting big problems with code, I like to write, garden, or spend time with my fiancée and three children.
    </p>
    <a id="download-cv" href="./jens-roland-cv.pdf" download>Download CV</a>
  </div>
</template>

<style scoped>
.sidebar {
  position: absolute;
  top: 0;
  left: 0;
  width: 500px;
  max-width: 100%;
  padding: 50px;
}
.sidebar > h2 {
  font-family: var(--font-headings-serif);
  font-weight: 400;
  font-size: 2.2rem;
}
.sidebar > p,
.sidebar > ul {
  margin-bottom: 1.2rem;
}
.sidebar > ul {
  padding-inline-start: 48px;
}
.sidebar > ul > li {
  list-style: none;
  margin: 0 0 1em;
}
.sidebar > ul > li::before {
  content: '';
  display: block;
  position: absolute;
  left: -48px;
  top: 0.3em;
  width: 38px;
  height: 38px;
  background-size: contain;
  background-repeat: no-repeat;
  filter: saturate(0.6);
  opacity: 0.7;
}
.sidebar > ul > li.logo-rayintelligence::before {
  background-image: url(/src/assets/employers/rayintelligence.png);
}
.sidebar > ul > li.logo-audienceproject::before {
  background-image: url(/src/assets/employers/audienceproject.png);
}
.sidebar > ul > li.logo-electrolux::before {
  background-image: url(/src/assets/employers/electrolux.png);
}

.social-links {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: normal;
  align-content: normal;
  margin-top: 1rem;
  margin-bottom: 3rem;
}
.social-links > a {
  display: block;
  flex-grow: 0;
  flex-shrink: 1;
  flex-basis: auto;
  align-self: auto;
  order: 0;
  text-align: center;
  text-decoration: none;
  color: var(--vt-c-black-soft);
  font-family: var(--font-headings-sans);
  font-size: 1.1rem;
}
.social-links > a > p {
  font-weight: 300;
}

.social-links > a {
  mix-blend-mode: multiply;
  filter: grayscale(0.4);
  opacity: 0.6;
  transition: all 0.4s ease-in-out;
}
.social-links > a > .logo {
  display: inline-block;
  height: 75px;
  max-width: 18vw;
  background-position: center bottom;
  background-repeat: no-repeat;
  background-size: contain;
  transition: all 0.2s ease-in-out;
}

.logo.github {
  background-image: url('/src/assets/social-icons/github.webp');
  width: 79px;
}
.logo.linkedin {
  background-image: url('/src/assets/social-icons/linkedin.webp');
  width: 76px;
}
.logo.stackoverflow {
  background-image: url('/src/assets/social-icons/stackoverflow.webp');
  width: 68px;
}
.logo.email {
  background-image: url('/src/assets/social-icons/email.webp');
  width: 107px;
}

.social-links:hover > a {
  filter: grayscale(1);
  opacity: 0.3;
}
.social-links > a:hover {
  filter: none;
  opacity: 1;
}
.social-links > a:hover > .logo {
  transform: scale(1.2) rotate(1.02turn) translateY(-0.4rem);
}

#portrait-background {
  position: relative;
  width: 930px;
  max-width: none;
  top: -50px;
  left: -282px;
  background-repeat: no-repeat;
}

#download-cv {
  display: block;
  height: 62px;
  margin: 3rem 0 1rem;
  background: rgb(143 143 143 / 15%) url(/src/assets/pdf-icon.svg) no-repeat -8px center;
  padding-left: 70px;
  font-size: 1.8rem;
  color: #8c8c8c;
  font-family: var(--font-headings-sans);
  font-weight: 300;
  text-decoration: none;
  line-height: 62px;
  border-radius: 0.7rem;
  transition: all 0.2s ease;
  user-select: none;
}

#download-cv:hover {
  background: #869cb6 url(/src/assets/pdf-icon.svg) no-repeat -8px center;
  color: #e9e9e0;
  padding-left: 80px;
  font-weight: 400;
}


/* Full desktop experience */
@media only screen and (min-width: 1280px) {
}

/* Mobile & Tablet */
@media only screen and (max-width: 1280px) {

  .sidebar {
    position: relative;
    padding: 1rem;
    margin: 0 auto;
  }
  .social-links {
    max-width: 100%;
    margin-bottom: 2rem;
  }
  #portrait-background {
    display: none;
  }

}

</style>
