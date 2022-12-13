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
import useEventSpace from '@/use/event-space'
//import useMapping from '@/use/mapping'
export default {
  name: 'CompositionApi',
  setup() {
    return useEventSpace() //Call this composition function
    //best practice when we use 2 or more imports
    /*const { capacity, attending, spacesLeft, increaseCapacity } = useEventSpace();
    const { map, embedId } = useMapping();

    return { capacity, attending, spacesLeft, increaseCapacity, map, embedId };*/
  }
}

</script>

<style scoped>

</style>