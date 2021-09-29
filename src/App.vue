<template>
  <div id="app" > 
    <div v-for="(album, index) in albums" :key="index">
      <Product :title="album.title" :author="album.author" :poster="album.poster"
      />
    </div>
  </div>
</template>

<script>
import Product from './components/Product.vue'
import axios from "axios";

export default {
  name: 'App',
  components: {
    Product,
  },
  data(){
    return {
      albums : [],
    }
  },
  // Quando il DOM è pronto e inizia a d essere mostrato
  mounted(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((response) => {
      console.log(response);
      const result = response.data;
      console.log(result.response); //oggetto dell'array
      this.albums = result.response;
      console.log(this.albums);
    });
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
