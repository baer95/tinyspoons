<script setup>
import CreppyMonday from '@/assets/images/creppy-monday.png'

const spoons = [
  {
    title: 'Hoe laat is het? Solidaritijd!',
    // image: 'https://extinctionrebellion.nl/app/uploads/2019/10/X-symbol-richBlack.svg',
    // text: '',
    link: 'https://extinctionrebellion.nl/',
  },
  {
    title: 'It gets better',
    // image: 'https://www.google.com/chrome/static/images/chrome-logo.svg',
    text: 'Or does it?',
    link: 'https://www.instagram.com/p/DChPkd-RJJE/',
  },
  {
    title: 'Crappy Monday? Crêppy Monday!',
    image: CreppyMonday,
    text: 'Food to heal your precious soul',
    link: 'https://www.instagram.com/p/DAn9CHxIozz/',
  },
  {
    title: 'Lets go shake again',
    image: 'https://imgproxy.ra.co/_/quality:66/w:1442/rt:fill/aHR0cHM6Ly9pbWFnZXMucmEuY28vZWY2YWExOGI5NTAzYTZkNWM0MzE2OWEyZGMwNDE5MjI0NGNkZjE3OS5qcGc=',
    text: 'It\' s way too long so someone had to make an executive decision.',
    link: 'https://shop.eventix.io/68c42916-cc69-490b-8328-74832008d056/tickets',
  },
]

let randomNumber = Math.floor(Math.random() * spoons.length)
</script>

<template>
  <div class="spoon">

    <h1 v-if="'title' in spoons[randomNumber]">{{ spoons[randomNumber].title }}</h1>

    <img v-if="'image' in spoons[randomNumber]" alt="Spoon Image" :src="spoons[randomNumber].image" />

    <p v-if="'text' in spoons[randomNumber]">{{ spoons[randomNumber].text }}</p>

    <a v-if="'link' in spoons[randomNumber]" :href="spoons[randomNumber].link">{{spoons[randomNumber].link}}</a>
  </div>
</template>

<style scoped>
div.spoon {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

div.spoon img {
  height: 40vh;
}
</style>
