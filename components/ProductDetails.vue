<template>
    <div class="card">
        <div class="grid grid-cols-2 gap-10">
            <div class="p-7">
                <img :src="product.image" alt="product img" class="mx-auto my-7">
            </div>
            <div class="p-7">
                <h2 class="text-4xl my-7">{{ product.title }}</h2>
                <p class="text-xl my-7">Price - ${{ product.price }}</p>
                <h3 class="font-bold border-b-2 mb-4 pb-2">Product description:</h3>
                <p  class="mb-7">{{ product.description }}</p>
                <div class="flex items-center gap-4">
                    <button class="btn flex">
                        <i class="material-icons mr-2">{{sign}}</i>
                        <span class="text-base" @click="pend">{{x}}</span>
                    </button>
                    <button @click="$router.back" class="btn flex">
                        <i class="material-icons mr-2">home</i>
                        <span class="text-base">Go Back</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    const { product } = defineProps(['product']);
    const x = ref('Add to cart');
    const sign = ref('add_shopping_cart');
    function pend(){
        x.value = 'Feature is not available';
        sign.value = 'warning';
        setTimeout(() => {
            x.value = 'Add to cart';
            sign.value = 'add_shopping_cart';
        }, 1500);
    }
</script>

<style scoped>
    img {
        max-width: 400px;
    }
</style>