<script setup>
import { ref } from 'vue'

const tasks = ref([
  { name: 'Boodschappen doen', completed: false },
  { name: 'Afwassen', completed: true },
  { name: 'Hond uitlaten', completed: false }
])


function toggleTask(task){
  task.completed = !task.completed
}
</script>

<template>
  <div>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <strong>{{ task.name }}</strong>
        ({{ task.completed ? 'voltooid' : 'niet voltooid' }})

           
        <button @click="toggleTask(task)">Toggle</button>
      </li>
    </ul>
  </div>
</template>
