<script setup>
import { computed, ref } from 'vue'

import Acid from '@/assets/images/acid.jpg'
import AdeWednesday from '@/assets/images/ade-wednesday.jpg'
import AtTheGetTogether from '@/assets/images/at-the-get-together.jpg'
import CreppyMonday from '@/assets/images/creppy-monday.png'
import MakingNecklaces from '@/assets/images/making-necklaces.jpg'

const boomDays = ref(0);
const boomHours = ref(0);
const boomMinutes = ref(0);
const boomSeconds = ref(0);

function updateBoomCountdown() {
  const oneDay = 60*60*24;
  const oneHour = 60*60;
  const oneMinute = 60;
  let diffInSeconds = Math.trunc((new Date(2025, 6, 17).getTime() - new Date().getTime()) / 1000); // getTime returns milliseconds
  boomDays.value = Math.trunc(diffInSeconds/60/60/24);
  boomHours.value = Math.trunc((diffInSeconds-boomDays.value*oneDay)/60/60);
  boomMinutes.value = Math.trunc((diffInSeconds-boomDays.value*oneDay-boomHours.value*oneHour)/60);
  boomSeconds.value = Math.trunc(diffInSeconds-boomDays.value*oneDay-boomHours.value*oneHour-boomMinutes.value*oneMinute);
  setTimeout(updateBoomCountdown, 1000);
}

updateBoomCountdown();

// eslint-disable-next-line no-unused-vars
const copyPasteThis = [
  {
    title: '',
    image: '',
    text: '',
    link: '',
  },
];

const spoons = [
  {
    title: 'Countdown to Boom Town',
    image: 'https://www.boomfestival.org/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fdancer%20(2).9296a51c.png&w=2048&q=75',
    text: computed(() => `Can you believe we're going there in ${boomDays.value}d ${boomHours.value}h ${boomMinutes.value}m ${boomSeconds.value}s ?`),
    link: 'https://www.boomfestival.org/',
  },
  {
    title: 'Thylacine set',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/LesEscales2019Thylacine_02.jpg/2560px-LesEscales2019Thylacine_02.jpg',
    text: 'imagine this: what if a really talented medieval peasant had access to CDJs',
    link: 'https://soundcloud.com/thylacinew/thylacine-live-with-instruments-fusion-festival-2022',
  },
  {
    title: 'Fédra\'s Hungarian Bangers',
    text: 'dit is mijn sterrenstof',
    link: 'https://open.spotify.com/playlist/1ngbA4MdYM36K3hLdukpZP?si=pt82AV9yS7i58qBHD0HFZw&pi=e-KEwjLvngRlKz',
  },
  {
    image: AtTheGetTogether,
  },
  {
    image: Acid,
  },
  {
    image: AdeWednesday,
    text: 'If you ever feel down, remember that the earth is 4.5 billion years old and we get to exist at the same time as molly',
  },
  {
    image: MakingNecklaces,
    text: 'We are always just one phone call away',
  },
  {
    title: 'Crêppy Monday',
    image: CreppyMonday,
    text: 'All Crêpes Are Beautiful',
  },
  {
    title: 'New Year\'s day plans',
    image: 'https://imgproxy.ra.co/_/quality:66/w:1442/rt:fill/aHR0cHM6Ly9pbWFnZXMucmEuY28vZWY2YWExOGI5NTAzYTZkNWM0MzE2OWEyZGMwNDE5MjI0NGNkZjE3OS5qcGc=',
    link: 'https://shop.eventix.io/68c42916-cc69-490b-8328-74832008d056/tickets',
  },
  {
    title: 'Everything will be okay.',
    text: 'But seriously, what the fuck?',
  },
]

let randomNumber = Math.floor(Math.random() * spoons.length)
</script>

<template>
  <div class="spoon">

    <h1 v-if="'title' in spoons[randomNumber]">{{ spoons[randomNumber].title }}</h1>

    <img v-if="'image' in spoons[randomNumber]" alt="Spoon Image" :src="spoons[randomNumber].image" />

    <p v-if="'text' in spoons[randomNumber]">{{ spoons[randomNumber].text }}</p>

    <a v-if="'link' in spoons[randomNumber]" :href="spoons[randomNumber].link" class="button">Click me</a>
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

a.button {
  color: white;
  background-color: hsla(160, 100%, 37%, 1);;
  padding: 15px 32px;
  font-size: 16px;
}
a.button:hover {
  box-shadow: 3px 3px 8px grey; /* <offset-x> <offset-y> <blur-radius> <color> */
}
a.button:active {
  box-shadow: none;
}
</style>
