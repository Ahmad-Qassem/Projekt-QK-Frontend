<script setup lang="ts">
import EntityList from '../components/EntityList.vue'

interface BodyMassTrack {
  id: number
  alter: number
  größe: number
  gewicht: number
  datum: string
  bmi: number
}

const bodyMassTrackList: BodyMassTrack[] = [
  { id: 1, alter: 25, größe: 180, gewicht: 75, datum: '15.01.2025', bmi: 23.1 },
  { id: 2, alter: 30, größe: 170, gewicht: 68, datum: '20.02.2025', bmi: 23.5 },
  { id: 3, alter: 22, größe: 175, gewicht: 70, datum: '10.03.2025', bmi: 22.9 },
  { id: 4, alter: 35, größe: 185, gewicht: 85, datum: '05.04.2025', bmi: 24.7 },
  { id: 5, alter: 28, größe: 165, gewicht: 62, datum: '12.05.2025', bmi: 22.7 }
]
</script>

<template>
  <div class="container">
    <h1>Body Mass Track</h1>
    <EntityList :entities="bodyMassTrackList" />
  </div>
</template>

<style scoped>
.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 2rem;
}

h1 {
  text-align: center;
  margin-bottom: 1.5rem;
}
</style>
