<script setup>
import { reactive } from 'vue'

const emit = defineEmits(['place-data'])

const searchTerm = reactive({
  query: '',
  timeout: null,
  results: null,
})

const handleSearch = () => {
  clearTimeout(searchTerm.timeout)
  searchTerm.timeout = setTimeout(async () => {
    console.log(searchTerm.query)
  }, 500)
}
</script>

<template>
  <div>
    <!-- search field -->
    <form>
      <div
        class="bg-white border border-indigo-600/30 rounded-lg shadow-lg flex items-center"
      >
        <i class="fa-solid fa-magnifying-glass p-2 text-indigo-600"></i>
        <input
          type="text"
          placeholder="Search for a place"
          class="rounded-r-lg p-2 border-0 outline-0 focus:ring-2 focus:ring-indigo-600 ring-inset w-full"
          v-model="searchTerm.query"
          @input="handleSearch"
        />
      </div>
    </form>
  </div>
</template>
