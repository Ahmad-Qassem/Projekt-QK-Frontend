<script setup lang="ts">
interface BodyMassTrack {
  id: number
  alter: number
  größe: number
  gewicht: number
  datum: string
  bmi: number
}

defineProps<{
  entities: BodyMassTrack[]
}>()
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Alter</th>
        <th>Größe (cm)</th>
        <th>Gewicht (kg)</th>
        <th>Datum</th>
        <th>BMI</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in entities" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.alter }}</td>
        <td>{{ item.größe }}</td>
        <td>{{ item.gewicht }}</td>
        <td>{{ item.datum }}</td>
        <td>{{ item.bmi }}</td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  background-color: white;
}

th, td {
  border: 1px solid #ccc;
  padding: 0.5rem;
  text-align: left;
}

th {
  background-color: #f5f5f5;
  color: black;
}

td {
  color: black;
}
</style>
