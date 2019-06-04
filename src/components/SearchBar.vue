<template>
  <form class="form-container" v-on:submit.prevent="fetchData()">
    <input class="input" type="text" placeholder="search photos!" v-model="query"/>
    <label v-if="this.error">No results found</label>
  </form>
</template>

<script>
import apiKey from '../../apiKey.js'
export default {
  name: 'SearchBar',
  data () {
    return {
      query: '',
      error: false
    }
  },
  methods: {
    async fetchData () {
      const response = await fetch(`https://api.unsplash.com/search/photos?query=${this.query}&per_page=12&orientation=landscape&client_id=${apiKey}`);
      const data = await response.json();
      if(!data.total) {
        this.error = true;
      } else {
        this.query = '';
        this.$emit('clicked', data)
        this.error = false;
      }
    }
  }
}
</script>

<style scoped>
.form-container {
  margin-left: 20px;
  margin-bottom: -2px;
}
.input {
  height: 44px;
  border-radius: 22px;
  width: 400px;
  font-size: 1.2rem;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border: none;
  outline: none;
  padding-left: 20px;
}
label {
  margin-left: 10px; 
}
</style>
