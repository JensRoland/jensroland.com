<script setup lang="ts">

</script>

<template>
  <div class="cover-story">
    <p>I used to spy on my brother.</p>
    <p>Kresten was six years older than me, he had his own room, a yellow Sony Walkman, and a bike with 18 gears. If you ever had an older brother	like mine, you know that Kresten was a <em>God</em>, and his room a forbidden realm of magic and mystery.</p>
    <p>On one of my expeditions into this realm, I found treasure. Sheets filled with jumbled up letters, numbers and arcane-looking symbols arranged into groups of five. An alien language! I knew the letters were from our cousin, who was widely considered a math prodigy; who knew what delicious secrets were hidden in those pages?</p>
    <br>
    <p><em>I had to know.</em></p>
    <br>
    <p>The school library had a book on cryptography, and I devoured it. Armed with my new knowledge of ciphers and their weaknesses, I returned to the mysterious scripts. The first substitution cipher fell easily to the frequency analysis and chosen-plaintext attacks from the book. First <em>&ldquo;e&rdquo;</em>, then <em>&ldquo;r&rdquo;</em>, and so on, each deciphered letter revealing more of the hidden message until my brother's secrets were mine.</p>
    <p>My inevitable gloating at cracking my brother's simple cipher only made my nemesis escalate to ever more complex ones: Caesar, Vigenère, Ottendorf, Alberti. One by one, I would learn their weaknesses and crack them. What was in the letters no longer mattered. I was <em>hooked</em>. I was Alan Turing at Bletchley Park. I was eight, and I had discovered cryptanalysis.</p>
  </div>
</template>

<style scoped>
.cover-story {
  font-size: 1.4em;
  text-align: justify;
  width: 640px;
  max-width: 100%;
  margin: 0 auto;
}
.cover-story > p {
  margin-bottom: 0.65rem;
}


/* Full desktop experience */
@media only screen and (min-width: 1280px) {
}

/* Mobile & Tablet */
@media only screen and (max-width: 1280px) {
  .cover-story {
    font-size: 1.1em;
  }
}
</style>
