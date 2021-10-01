<template>
   <form class="p-5" v-on:submit.prevent>
        <select name="genere" id="genere">
          <option value="genre" v-for="(element, indice) in arrayModificato" :key="indice">{{element}}</option>
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
        arrayModificato: String, 
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