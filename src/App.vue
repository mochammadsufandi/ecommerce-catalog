<script setup>
    import { ref, watchEffect } from 'vue';
    import ProductCardWomen from './components/ProductCardWomen.vue';
    import ProductCardMen from './components/ProductCardMen.vue';
    import ProductNotAvailable from './components/ProductNotAvailable.vue';
    import Background from './components/Background.vue';
    import ProductSkeletonWomen from './components/ProductSkeletonWomen.vue';
    import ProductSkeletonMen from './components/ProductSkeletonMen.vue';

    const product = ref();
    const productId = ref(1);
    const isLoading = ref(true);
    const fetchProducById = async(id=1) => {
        try {
            const response = await fetch(`https://fakestoreapi.com/products/${id}`);
            const responseData = await response.json();
            product.value = responseData;
            isLoading.value = false
            console.log(isLoading.value)
        
        } catch (err) {
            console.log(err);
        }
    }
    const rating = 5;
    const clickHandler = () => {
        productId.value += 1;
        isLoading.value = true;
        if(productId.value > 20) {
            productId.value = 1
        }
        fetchProducById(productId.value)
    }

    watchEffect(() => {
        fetchProducById()
    })

</script>

<template>
    <Background 
        :category="product.category"
    />
    <ProductSkeletonMen
        v-if="isLoading"
    />

    <ProductSkeletonWomen 
        v-else-if="isLoading && product.category === `women's clothing`" 
    />
    <ProductSkeletonMen
        v-else-if="isLoading && product.category === `men's clothing`" 
    />
    <div v-else>
        <ProductCardWomen 
        v-if="product.category === `women's clothing`" 
        :product="product" 
        :rating="rating"
        :onClick="clickHandler"
        />
        <ProductCardMen 
        v-else-if="product.category === `men's clothing`"
        :product="product"
        :rating="rating"
        :onClick="clickHandler"
        />
        <ProductNotAvailable 
            v-else
            :onClick="clickHandler"
        />
    </div>

</template>

<style scoped>
    .button {
        font-weight: bold;
        font-size: larger;
        border-style: solid;
        border-width: 1px;
        border-color: black;
        padding: 10px;
    }
</style>
