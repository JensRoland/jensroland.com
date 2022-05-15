<template>
  <a :href=url class="card">
    <figure>
      <img :src=image alt="Article image">
      <figcaption>{{title}}</figcaption>
    </figure>
  </a>
</template>

<script>
export default {
  props: {
    title: String,
    tags: Array,
    image: String,
    url: String
  }
}
</script>

<style scoped>
figure > figcaption {
  font-size: 1.1em;
  padding: 0 0.8em;
}
figure > img {
  max-width: 100%;
}
</style>
