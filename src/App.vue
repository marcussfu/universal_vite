<script setup>
// import HelloWorld from './components/HelloWorld.vue'
import { reactive } from "vue";
let roomArray = reactive([]);

let arrayFromApi = [
  {
    id: 1,
    name: "AA",
    dealerImageSrc: "https://cdn.quasar.dev/img/parallax2.jpg",
  },
  {
    id: 2,
    name: "BB",
    dealerImageSrc: "https://cdn.quasar.dev/img/parallax2.jpg",
  },
  {
    id: 3,
    name: "CC",
    dealerImageSrc: "https://cdn.quasar.dev/img/parallax2.jpg",
  },
  {
    id: 4,
    name: "DD",
    dealerImageSrc: "https://cdn.quasar.dev/img/parallax2.jpg",
  },
  {
    id: 5,
    name: "EE",
    dealerImageSrc: "https://cdn.quasar.dev/img/parallax2.jpg",
  },
];

roomArray.push(...arrayFromApi);
</script>

<template>
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" /> -->
  <div class="q-pa-md row items-start q-gutter-md">
    <q-card v-for="room in roomArray" :key="room.id" class="my-card" flat bordered>
      <q-card-section horizontal>
        <q-card-section>
          {{ room.name }}
        </q-card-section>

        <q-img class="col-5" :src="room.dealerImageSrc" />
      </q-card-section>
    </q-card>
    <q-card v-ripple class="my-box cursor-pointer q-hoverable">
     <!-- <span class="q-focus-helper"></span> -->
     <q-card-section>
        ...
     </q-card-section>
</q-card>
  </div>
</template>

<style scoped>
.my-card {
  width: 100%;
  max-width: 400px;
}

.my-card:hover {
  max-width: 450px;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
