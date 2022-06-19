<template>
    <section class="products-list" :class="itemSelected && 'hide'">
        <ProductItem v-for="product in products" :key="product.name" :productInfo="product" @showDialog="showDialog" />
        <ChoicesDialog v-if="itemSelected" @closeDialog="itemSelected = false" :productInfo="specProductInfo"/>
        <Basket />
    </section>

</template>
<script>
import ProductItem from './ProductItem.vue'
import ChoicesDialog from './ChoicesDialog.vue'
import Basket from './Basket.vue'
export default {
    components: { ProductItem, ChoicesDialog, Basket },

    data() {
        return {
            products: [
                {
                    name: "Footlong-Doppelpack",
                    description: "2 Subs 30cm nach Wahl",
                    choiceOf: {
                        meat: ["Chicken", "Pan", "Salat"],
                        topping: ["cheese","ketchup"],
                        },
                    price: 17.99,
                
                },
                {
                    name: "Chicken Terayaki Sub",
                    description: "mit würzigen Hähnchenbruststreifen in Teriyaki-Marinade",
                    choiceOf: {
                        meat: ["Chicken", "Pig", "Cow"],
                        topping: ["mayo","alioli"],
                        },
                    price: 9.99
                },
            ],
            itemSelected: false,
            specProductInfo: {},


        }
    },
    methods: {
        showDialog(data) {
            this.itemSelected = true;
            this.specProductInfo = data;
        }
    },
}
</script>


<style scoped>
.products-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    position: relative;
    width: 100%;
    height: 100%;
}

.hide::after {
    content: "";
    position: absolute;
    top: -1rem;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.637);
}
</style>