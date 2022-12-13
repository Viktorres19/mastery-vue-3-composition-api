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
import { ref, computed } from 'vue'
export default {
  name: 'CompositionApi',
  setup() {
    const capacity = ref(4);
    const attending = ref(['Tim', 'Bob', 'Joe'])

    const spacesLeft = computed(() => {
      return capacity.value - attending.value.length
    })

    const increaseCapacity = () => {
      capacity.value++
    }
    return { capacity, attending, spacesLeft, increaseCapacity }
  }
}
</script>

<style scoped>

</style>