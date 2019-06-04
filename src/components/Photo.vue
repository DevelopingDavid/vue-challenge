<template>
  <section class="card-container">
    <img class="image" v-bind:src="result.urls.thumb"/>
  </section>
</template>

<script>
export default {
  name: "photo",
  props: ["result"],
  created() {
    console.log(this.result)  //undefined;
  },
};
</script>

<style scoped>
.card-container {
  width: 300px;
  display: flex;
  justify-content: center;
  height: 200px;
  align-items: center;
}

.image {
  width: 90%;
  height: 90%;
}
</style>

