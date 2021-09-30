<template>
    <div class="menu">
        <ul>
        <li>
            <a href="#">{{ genre }}</a>
        </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Selection",

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