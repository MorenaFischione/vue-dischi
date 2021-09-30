<template>

    <section>
        <div class="align-items-center">
            <img class="p-3 my_copertina" :src="poster" alt="">
            <h4>{{ title }}</h4>
            <p>{{ author }}</p>
            <p>{{ year }}</p>
        </div>
    </section>

  
   
 
</template>

<script>

export default {
    name: "Product",

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


    .my_copertina {
        height: 200px;
        object-fit: contain;
    }

    h4 {
        color: $colorPrincipale;
        font-family: $fontTitle;
        font-weight: 700;
        text-transform: uppercase;
    }

    p {
        color: $colorSecondary;
        font-family: $fontText;
    }

</style>