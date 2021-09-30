<template>
   <form class="p-5" v-on:submit.prevent>
        <select name="genere" id="genere">
          <option value="genre" @click="ricercaGenere">rock</option>
          <option value="genre">pop</option>
          <option value="genre">jazz</option>
          <option value="genre">metal</option>
        </select>
    </form>
</template>

<script>
export default {
    name: "Selection",

    data: function(){
        return {
            listaGeneri: [],
        }
    },

    methods: {
        ricercaGenere ()  {
            let self = this;
            return console.log(self.value);
        },

    },

    computed: {
        
    },

    props: {
        author: String,
        genre: String,
        poster: String,
        title: String,
        year: Number,
        
    },

}
</script>

<style lang="scss">
@import "../style/variables.scss";
    ul {
        list-style-type: none;
        padding: 10px;

        a {
        text-decoration: none;
        color: $colorBg;
        
        }
    }

    

</style>