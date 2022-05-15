<script setup lang="ts">
import ArticleItem from './ArticleItem.vue'
</script>

<template>
  <div class="articles">
    <header>
      <h2>Articles, Rants &amp; Ramblings</h2>
    </header>
    <div class="i-like-netflix">
      <div class="cards">
        <ArticleItem
          v-for="article in articles"
          :title="article.title"
          :image="article.image"
          :url="article.url"
          @mouseover="showArticleDetails(article)"
        ></ArticleItem>
      </div>
      <div class="details">
        <a
          v-for="article in articles"
          :href="article.url"
          :class="{ 'is-active': article===activeArticle }"
          :style="{ backgroundImage: `url(${article.largeImage})` }"
        >
          <ul class="tags">
            <li v-for="tag in article.tags">{{tag}}</li>
          </ul>
          <div class="details-content">
            <h3>{{article.title}}</h3>
            <p>{{article.description}}</p>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data: () => ({
    activeArticle: {},
    articles: [
      {
        title: 'On Leadership',
        description: 'Hiring the right people, giving them what they need, and getting out of the way.',
        textColor: '#e1e2e4',
        image: new URL('../assets/articles/pexels-cottonbro-4065145.webp', import.meta.url).href,
        largeImage: new URL('../assets/articles/pexels-cottonbro-4065145-large.webp', import.meta.url).href,
        url: 'https://www.linkedin.com/pulse/leadership-jens-roland/',
        tags: ['linkedin', 'leadership']
      },
      {
        title: 'On Developer Productivity',
        description: 'About no-blame culture, uninterrupted flow, and high trust in developer teams.',
        textColor: '#c0722a',
        image: new URL('../assets/articles/pexels-thisisengineering-3861958.webp', import.meta.url).href,
        largeImage: new URL('../assets/articles/pexels-thisisengineering-3861958-large.webp', import.meta.url).href,
        url: 'https://www.linkedin.com/pulse/developer-productivity-jens-roland/',
        tags: ['linkedin', 'leadership']
      },
      // {
      //   title: 'Another article to make you think, "Huh."',
      //   description: 'And the things were many and the stuff ran long, but they all had vewy gweat fwiends in Wome. Who had a wife, you know.',
      //   textColor: '#e1e2e4',
      //   image: new URL('../assets/articles/pexels-thisisengineering-3861958.webp', import.meta.url).href,
      //   largeImage: new URL('../assets/articles/pexels-thisisengineering-3861958-large.webp', import.meta.url).href,
      //   url: '#',
      //   tags: ['rants']
      // }
    ]
  }),
  mounted () {
    this.activeArticle = this.articles[0]
  },
  methods: {
    showArticleDetails (article:any) {
      this.activeArticle = article
    }
  }
}
</script>


<style scoped>
.articles {
  margin-bottom: 6rem;
}
.articles > header {
  display: flex;
  background: url(/src/assets/articles-header-background.webp) no-repeat center center / contain;
  width: 895px;
  max-width: 100vw;
  height: 258px;
  max-height: calc(100vw * (258 / 895));
  margin: 1rem auto;
  justify-content: center;
  align-items: center;
}
.articles > header > h2 {
  margin: 0 auto;
  font-family: var(--font-headings-serif);
  text-align: center;
  font-size: 3.5rem;
  text-shadow: 0px 0px 0.2em var(--color-background-card);
}
.i-like-netflix {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
  align-content: stretch;
}

.i-like-netflix > .cards {
  flex-grow: 0;
  flex-shrink: 1;
  flex-basis: auto;
  align-self: auto;
  order: 0;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-end;
  align-items: flex-start;
  align-content: flex-start;
}
.card {
  display: block;
  flex-grow: 0;
  flex-shrink: 1;
  flex-basis: auto;
  align-self: auto;
  order: 0;
  width: 350px;
  max-width: 80vw;
  height: 270px;
  max-height: calc(80vw * (270 / 350));
  margin: 2rem 2rem;
  overflow: hidden;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  background: var(--color-background-card);
  text-decoration: none;
  color: var(--color-text-on-card);
  transition: all 0.1s ease-in-out;
}
.card:hover {
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
  transform: scale(1.04) translateY(-0.2rem);
}
.card:active:hover {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  transform: scale(1) translateY(0);
}

/* Glossy effect */
.card::after {
    content: "";
    position: absolute;
    margin: auto;
    top: -4em;
    left: 45%;
    width: 100%;
    height: 100%;
    background: linear-gradient(to bottom, rgba(255, 255, 255, 0.3) 0%, rgba(255, 255, 255, 0) 100%);
    transform: rotate(-17deg);
}


.i-like-netflix > .details {
  display: block;
  flex-grow: 0;
  flex-shrink: 0;
  flex-basis: auto;
  align-self: center;
  order: 0;
  width: 435px;
  height: 668px;
  margin-left: 1rem;
  -webkit-mask-image: url(../assets/article-details-mask.webp);
  mask-image: url(../assets/article-details-mask.webp);
}
.i-like-netflix > .details > a {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  opacity: 0;
  color: var(--color-text);
  background-position-x: 0px;
  background-repeat: no-repeat;
  visibility: hidden;
  transition: all 1s ease 75ms;
}
.i-like-netflix > .details > a.is-active {
  opacity: 1;
  background-position-x: -30px;
  visibility: visible;
}

.i-like-netflix > .details > a > .details-content {
  display: block;
  opacity: 0;
  width: 100%;
  height: 52%;
  top: 58%;
  padding: 0.5rem 3.5rem 0 3.5rem;
  position: absolute;
  color: var(--vt-c-white-mute);
  background: rgba(0, 0, 0, 0.6);
  background: linear-gradient(0deg, transparent 0%, rgba(0, 0, 0, 0.6) 30%);
  transition: all 1s ease 75ms;
}
.i-like-netflix > .details > a > .details-content > h3 {
  color: var(--vt-c-white-mute);
  font-family: var(--font-headings-sans);
  font-weight: 200;
  font-size: 2.2rem;
  line-height: 1.3em;
  margin-bottom: 0.3rem;
}
.i-like-netflix > .details > a > .details-content > p {
  font-family: var(--font-headings-sans);
  font-weight: 300;
  font-size: 1.1rem;
}
.i-like-netflix > .details > a.is-active > .details-content {
  opacity: 1;
  top: 48%;
}

.tags {
  list-style: none;
  margin: 0;
  position: absolute;
  top: calc(48% - 2.4rem);
  padding: 0 3.5rem 0;
}
.tags > li {
  display: inline-block;
  padding: 0.2rem 0.4rem;
  background: var(--vt-c-pale-yellow);
  color: var(--vt-c-text-light-2);
  font-family: var(--font-headings-sans);
  font-size: 0.8rem;
  font-weight: 500;
  margin-right: 0.5rem;
  user-select: none;
}


/* Full desktop experience */
@media only screen and (min-width: 1280px) {
}

/* Mobile & Tablet */
@media only screen and (max-width: 1280px) {
  .articles {
    margin-bottom: 1rem;
  }
  .articles > header {
    margin: 2rem auto 0;
  }
  .articles > header > h2 {
    font-size: min(7vw, 3.5rem);
  }
}

/* Small screens */
@media only screen and (max-width: 850px) {
  .i-like-netflix > .details {
    display: none;
  }
  .i-like-netflix > .cards {
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    align-content: center;
  }
  .card {
    margin: 1rem;
  }
}

/* Devices not supporting hover */
@media (hover: none) {
  .i-like-netflix > .details {
    display: none;
  }
  .i-like-netflix > .cards {
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    align-content: center;
  }
  .card {
    margin: 1rem;
  }
}
</style>
