<template>
  <div class="photo-container">
    <Photo v-for="result in results" :result="result" :key="result.id"></Photo>
  </div>
</template>

<script>
import Photo from './Photo.vue';
export default {
  name: 'photoContianer',
  components: {
    Photo
  },
  props: [
    'results'
  ]
}
</script>

<style scoped>
.photo-container {
  display: flex;
  flex-wrap: wrap;
  margin: 20px 0;
}
</style>

