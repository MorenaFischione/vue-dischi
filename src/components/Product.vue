<template>
    <div class="container my_wrapper-album">
        <div class="row">
            <div class="col-12">
                    <h1>{{title}} {{author}} </h1>
                    <img :src="poster" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Product",
    props: {
        author: String,
        genre: String,
        poster: String,
        title: String,
        year: String,
    },
}
</script>

<style lang="scss">
.my_wrapper-album {
    width: 100%;
    height: 300px;

    img {
        width: 100%;
    }
}

</style>