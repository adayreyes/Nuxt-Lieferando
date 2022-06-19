<template>
    <section class="products-list" :class="itemSelected ? hide : ''">
        <ProductItem v-for="product in products" :key="product.name" :productInfo="product" @hide="itemSelected = true"  />
        <ChoicesDialog v-if="itemSelected" @closeDialog="itemSelected = false"/>
    </section>
    
</template>
<script>
import ProductItem from './ProductItem.vue'
import ChoicesDialog from './ChoicesDialog.vue'
export default {
    components: { ProductItem, ChoicesDialog },

    data() {
        return {
            products: [
                {
                    name: "Footlong-Doppelpack",
                    description:"2 Subs 30cm nach Wahl",
                    choiceOf: ["Chicken","Pan","Salat"],
                    price: 17.99,
                },
                {
                    name: "Chicken Terayaki Sub",
                    description:"mit würzigen Hähnchenbruststreifen in Teriyaki-Marinade",
                    choiceOf: ["30cm Sub", "15cm Sub"],
                    price: 9.99
                },
            ],
            itemSelected: false,
            hide: "hide"

        }
    },
}
</script>


<style scoped>
    .products-list{
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
     .hide::after{
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.637);
    }
</style>