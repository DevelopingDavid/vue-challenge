<template>
  <div id="app">
    <div class="searchBar"> 
      <h1>Finder</h1>
      <SearchBar @clicked="onClickChild" />
    </div>
    <PhotosContainer :results="results" /> 
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import PhotosContainer from './components/PhotosContainer.vue';

export default {
  name: 'app',
  data () {
    return {
      results: []
    }
  },
  components: {
    SearchBar,
    PhotosContainer
  },
   methods: {
    onClickChild (value) {
      this.results = value.results;
    }
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Open+Sans:300,400,700&display=swap');
* { 
  margin: 0;
}
.searchBar {
  display: flex;
  align-items: center;
  background-color: #247BA0;
  font-family: 'Open Sans', sans-serif;
  color: white;
  font-size: 1.7rem;
  padding-left: 20px;
  height: 100px;
}
</style>
