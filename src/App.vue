<script setup>
import Judul from "./components/Judul.vue";
import Page from "./components/Page.vue";
import PageA from "./components/PageA.vue";
import PageB from "./components/PageB.vue";
import { ref } from "vue";

// counter adalah sebuah reactive value
const counter = ref(0);
const nama = ref("");
const halaman = ref(0);
</script>

<template>
  <Judul>Hello Vue</Judul>
  <p>{{ counter }}</p>
  <button @click="counter++">Click</button>

  <div>
    <!-- model binding -->
    <input type="text" v-model="nama" />
    <p>
      Hello
      <span v-if="nama">{{ nama }}</span>
      <span v-else>World</span>
    </p>
  </div>

  <select v-model="halaman">
    <option :value="0">Halaman 1</option>
    <option :value="1">Halaman 2</option>
    <option :value="2">Halaman 3</option>
  </select>
  <Page v-if="halaman === 0">Halaman 1</Page>
  <PageA v-if="halaman === 1" />
  <PageB v-if="halaman === 2" />
</template>

<style scoped></style>
