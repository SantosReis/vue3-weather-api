<script setup>
import { ref } from 'vue'
import SearchInput from './components/SearchInput.vue'

const places = ref([])

const addPlace = (data) => {
  console.log(data)
}
</script>
<template>
  <main>
    <!-- Date -->
    <div class="text-center mb-6">
      {{
        new Date().toLocaleDateString('en-us', {
          weekday: 'long',
          year: 'numeric',
          month: 'long',
          day: 'numeric',
        })
      }}
    </div>

    <!-- Search -->
    <div><SearchInput @place-data="addPlace" /></div>
  </main>
</template>
