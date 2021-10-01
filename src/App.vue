<template>
  <div id="app">
    <div class="header">
      <img class="logo" src="https://cantabrialabsdifacooper.it/wp-content/uploads/2021/03/png-clipart-spotify-logo-spotify-computer-icons-podcast-music-apps-miscellaneous-angle.png" alt="">
    </div>
    <div class="d-flex justify-content-center">
      <div>
          <Selection :arrayModificato="arrayGeneri"
          />
      </div>
    </div>
    <div class="main">
      <div class="d-flex flex-wrap justify-content-evenly my_container " > 
        <div v-for="(album, index) in albums" :key="index" class="card">
          <Product :title="album.title" :author="album.author" :age="album.year" :poster="album.poster" :genre="album.genre" 
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Product from './components/Product.vue'
import axios from "axios";
import Selection from "./components/Selection.vue";

export default {
  name: 'App',
  components: {
    Product,
    Selection,
  },
  data(){
    return {
      albums : [],
      arrayGeneri:[],
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
    });console.log(this.albums);
  },

    methods: {
        listaGeneri ()  {
          let self = this;
            console.log(self.albums);
            for(let i=0; i < self.albums.length; i++){
              console.log(self.albums[i]);
              let genere = self.albums[i].genre;
              console.log(genere);
              if (!self.arrayGeneri.includes(genere)){
                  self.arrayGeneri.push(genere);
              }
            } console.log(self.arrayGeneri);
        },

    },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "./style/variables.scss";
#app {


  .header {
    height: 80px;
    background-color: $colorBg;

    .logo {
      width: 80px;
      background-color: $colorBg;
    }
  }
  
  .main {
    background-color: $bgPrincilale;
  }

  .my_container {
    width: 80%;
    margin: 0 auto;
  }

  .card {
    width: calc(100% / 5 - 50px);
    background-color: $colorBg;
    margin-bottom: 20px;
    margin-top: 20px;
  }

}
</style>