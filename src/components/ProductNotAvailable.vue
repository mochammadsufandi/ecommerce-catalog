<script setup>
    defineProps({
        onClick : Function
    })
</script>

<template>
    <div class="product-card">
        <img src="../assets/sad.png"/>
        <div class="product-explanation">
            <p>This product is unavailable to show</p>
            <button 
                class="not-available"
                @click="onClick"
            >
                Next Product
            </button>
            
        </div>
    </div>
</template>

<style scoped>
    .product-card > img {
        opacity: 0.25;
        height: 75%;
        align-self: center;
        margin-left: auto;
        margin-right: auto;
    }
    .product-explanation {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
    }
    .product-explanation > p {
        text-align: center;
        font-size: 20px;
    }
    .product-explanation .not-available {
        width: 465px;
        height: 42px;
        box-sizing: border-box;
        font-size: 20px;
        font-weight: 600;
        margin: 0.5rem 0 0;
        color: var(--categoryText);
        border: 3px solid black;
    }
</style>