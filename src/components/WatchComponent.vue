<template>
  <div>
    Search for <input v-model="searchInput" />
    <div>
      <p>Number of events: {{ results }}</p>
    </div>
  </div>
</template>

<script>
//watch Effect is new for Vue 3
import { ref, watchEffect } from '@vue/composition-api'
import eventApi from '@/api/event.js'
export default {
  name: 'WatchComponent',
  setup() {
    const searchInput = ref('')
    const results = ref(0)

    watchEffect(() => {
      results.value = eventApi.getEventCount(searchInput.value)
    })

    return { searchInput, results }
  }
}
</script>

<style scoped>

</style>