<script setup lang="ts">
import { ref, onMounted } from 'vue'
import EntityList from '../components/EntityList.vue'

interface BodyMassTrack {
  id: number
  alter: number
  größe: number
  gewicht: number
  datum: string
  bmi: number
}

const bodyMassTrackList = ref<BodyMassTrack[]>([])
function loadEntities() {
  const baseUrl = import.meta.env.VITE_BACKEND_BASE_URL
  const endpoint = `${baseUrl}/bmi`

  fetch(endpoint)
  .then((response) => response.json())
  .then((result: BodyMassTrack[]) => {
  bodyMassTrackList.value = result
  })
  .catch((error) => console.log('Fehler beim Laden:', error))
  }
  onMounted(() => {
  loadEntities()

})

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
