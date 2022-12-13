<template>
  <div>
    <p>Capacity: {{ capacity }}</p>
    <button @click="increaseCapacity()">Increase Capacity</button>
    <h2>Attending</h2>
    <p>Spaces Left: {{ spacesLeft }} out of {{ capacity }} </p>
    <ul>
      <li v-for="(name, index) in attending" :key="index">
        {{ name }}
      </li>
    </ul>
  </div>
</template>

<script>
import { reactive, computed, toRefs } from 'vue'
export default {
  name: 'CompositionApi',
  setup() {
    const event = reactive({
      capacity: 4,
      attending: ['Tim', 'Bob', 'Joe'],
      spacesLeft: computed(() => {
        return event.capacity - event.attending.length
      })
    })

    const increaseCapacity = () => {
      event.capacity++
    }
    return { ...toRefs(event), increaseCapacity }
  }
}
</script>

<style scoped>

</style>