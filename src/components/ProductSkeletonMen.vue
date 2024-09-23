<script setup>

</script>

<template>
    <div class="product-skeleton">
        <div class="product-image">
            <div></div>
        </div>
        <div class="product-explanation">
            <h1></h1>
            <div class="category">
                <p></p>
                <div class="rating-box">
                    <p></p>
                    <div>
                        <div class='rating-level-up'></div>
                        <div class='rating-level-up'></div>
                        <div class='rating-level-up'></div>
                        <div class='rating-level-up'></div>
                        <div class='rating-level-up'></div>
                    </div>
                </div>
            </div>
            <div class="description">
                <p class="p1"></p>
                <p class="p2"></p>
                <p class="p3"></p>
            </div>
            <div class="price"></div>
            <button class="buy-now">Buy Now</button>
            <button class="next-product">Next Product</button>
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
    .product-image div {
        width: 100%;
        height: 75%;
        border-radius: 10px;
        animation: pulse 2s infinite ease-in-out;
    } 
    .product-explanation {
        padding: 50px 1rem 1rem;
        width: 57%;
    }
    .product-explanation h1 {
        width: 100%;
        height: 28px;
        animation: pulse 2s infinite ease-in-out;
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
        width: 10rem;
        height: 18px;
        animation: pulse 2s infinite ease-in-out;
    }
    .product-explanation .rating-box > p {
        display: inline-block;
        padding: 0 0.5rem 0;
        width: 3rem;
        height: 18px;
        animation: pulse 2s infinite ease-in-out;
    }
    .product-explanation .rating-box div {
        display: inline-block;
    }
    .product-explanation .rating-box .rating-level-up {
        width: 18px;
        height: 18px;
        display: inline-block;
        margin-right: 1px;
        border-radius: 50%;
        animation: pulse 2s infinite ease-in-out;
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
    .product-explanation .description .p1 {
        width: 100%;
        height: 20px;
        margin-bottom: 10px;
        animation: pulse 2s infinite ease-in-out;
    }
    .product-explanation .description .p2 {
        width: 75%;
        height: 20px;
        margin-bottom: 10px;
        animation: pulse 2s infinite ease-in-out;
    }
    .product-explanation .description .p3 {
        width: 60%;
        height: 20px;
        margin-bottom: 10px;
        animation: pulse 2s infinite ease-in-out;
    }
    .product-explanation .price {
        padding: 0.5rem 0;
        width: 5rem;
        height: 28px;
        margin-bottom: 5px;
    }
    .product-explanation .buy-now {
        width: 259px;
        height: 42px;
        box-sizing: border-box;
        background-color: var(--headerProductText2);
        font-size: 20px;
        font-weight: 600;
        color: var(--productCardBG);
        margin-right: 1rem;
    }
    .product-explanation .next-product {
        width: 259px;
        height: 42px;
        box-sizing: border-box;
        font-size: 20px;
        font-weight: 600;
        color: var(--headerProductText1);
        margin-right: 1rem;
        border: 3px solid var(--headerProductText2);
    }

    @keyframes pulse {
        0% {
            background-color: rgb(214, 215, 240);
        }

        50% {
            background-color: rgb(195, 196, 241);
        }

        100% {
            background-color: rgb(166, 168, 235);
        }
    }
</style>