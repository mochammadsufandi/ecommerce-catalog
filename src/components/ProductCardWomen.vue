<script setup>
defineProps({
    product : Object,
    rating : Number,
    onClick : Function
})

</script>

<template>
    <div class="product-card">
        <div class="product-image">
            <img :src="product.image"/>
        </div>
        <div class="product-explanation">
            <h1>{{product.title}}</h1>
            <div class="category">
                <p>{{product.category}}</p>
                <div class="rating-box">
                    <p>{{ product.rating.rate }}/5</p>
                    <div v-for="(value,index) in rating" :key="index">
                        <div v-if="index < product.rating.rate" class='rating-level-up'></div>
                        <div v-else class='rating-level-down'></div>
                    </div>

                </div>
            </div>
            <div class="description">
                {{ product.description }}
            </div>
            <div class="price">
                ${{ product.price }}
            </div>
            <button class="buy-now">Buy Now</button>
            <button 
                class="next-product"
                @click="onClick"
            >
                Next Product
            </button>
        </div>
    </div>
</template>

<style scoped>
    .product-image {
        width: 305.81px;
        height: 100%;
        align-content: center;
        padding: 5px;
        box-sizing: border-box;
        margin: 0 3rem;
    }
    .product-image img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    } 
    .product-explanation {
        padding: 50px 1rem 1rem;
        width: 57%;
    }
    .product-explanation h1 {
        font-size: 28px;
        font-weight: 600;
        color: var(--headerProductText1);
    }
    .product-explanation .category {
        display: flex;
        justify-content: space-between;
        padding: 3px 0 3px;
        margin-top: 1rem;
        border-style: solid;
        border-color: black;
        border-width: 0 0 1px;
        border-color: rgba(0,0,0,0.2);
    }
    .product-explanation .category > p {
        display: inline-block;
        color: var(--categoryText);
        font-size: 18px;
        font-weight: 400;
    }
    .product-explanation .rating-box > p {
        display: inline-block;
        padding: 0 0.5rem 0;
        font-size: 18px;
        font-weight: 400;
        color: var(--categoryText);
    }
    .product-explanation .rating-box div {
        display: inline-block;
    }
    .product-explanation .rating-box .rating-level-up {
        background-color: var(--headerProductText1);
        width: 18px;
        height: 18px;
        display: inline-block;
        margin-right: 1px;
        border-radius: 50%;
    }
    .product-explanation .rating-box .rating-level-down {
        width: 18px;
        height: 18px;
        display: inline-block;
        margin-right: 1px;
        border-radius: 50%;
        border-color: var(--headerProductText1);
        border-width: 1px;
    }
    .product-explanation .description {
        padding: 1rem 0;
        height: 45%;
        box-sizing: border-box;
        font-size: 20px;
        border-style: solid;
        border-width: 0 0 1px;
        border-color: rgba(0,0,0,0.2);
        overflow-y: scroll;
    }
    .product-explanation .price {
        padding: 0.5rem 0;
        font-size: 28px;
        font-weight: 600;
    }
    .product-explanation .buy-now {
        width: 259px;
        height: 42px;
        box-sizing: border-box;
        background-color: var(--headerProductText1);
        font-size: 20px;
        font-weight: 600;
        color: var(--productCardBG);
        margin-right: 1rem;
    }
    .product-explanation .buy-now:hover {
        background-color: #ed5fd8;
    }
    .product-explanation .next-product {
        width: 259px;
        height: 42px;
        box-sizing: border-box;
        font-size: 20px;
        font-weight: 600;
        color: var(--headerProductText1);
        margin-right: 1rem;
        border: 3px solid var(--headerProductText1);
    }
    .product-explanation .next-product:hover {
        background-color: #ed5fd8;
        color: var(--productCardBG);
    }
</style>