<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <CompositionApi />
  </div>
</template>

<script>

import CompositionApi from '@/components/CompositionApi.vue'

export default {
  name: 'HomeView',
  components: { CompositionApi }
}
</script>
