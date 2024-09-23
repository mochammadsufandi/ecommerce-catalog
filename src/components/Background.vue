<script setup>
    defineProps({
        category : String
    })
    const number = 20;
</script>

<template>
    <div v-if="category === `women's clothing`" class="background1">
        <div v-for="val in number" class="container"> 
            <img  class="img1" src="../assets/push-pins.png" alt="">
            <img  class="img2" src="../assets/bulb.png" alt="">
            <img  class="img3" src="../assets/doodle-stars.png" alt="">
            <img  class="img4" src="../assets/abstract-christmas-tree.png" alt="">
        </div>
    </div>
    <div v-else class="background2">
        <div v-for="val in number" class="container"> 
            <img  class="img1" src="../assets/push-pins.png" alt="">
            <img  class="img2" src="../assets/bulb.png" alt="">
            <img  class="img3" src="../assets/doodle-stars.png" alt="">
            <img  class="img4" src="../assets/abstract-christmas-tree.png" alt="">
        </div>
    </div>
</template>

<style scoped>
    .container {
        opacity: 30%;
        margin: 1rem 0.5rem;
        width: 21%;
        transform: translateX(3rem);
    }

    img {
        display: inline-block;
        position: relative;
        width: 2rem;
        height: 2rem;
    }

    .img1 {
        margin: 0 1.5rem
    }
    .img2 {
        transform: translateY(-5rem);
        margin: 5rem 1.5rem;
    }
    .img3 {
        margin: 0 1.5rem
    }
    .img4 {
        transform: translateY(-5rem);
        margin: 5rem 1.5rem;
    }
</style>