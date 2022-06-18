<template>
    <section class="restaurants-list">
        <RestaurantItem v-for="restaurant in restaurants" :key="restaurant.name" :restaurantInfo="restaurant"/>
    </section>
</template>
<script>
import RestaurantItem from './RestaurantItem.vue'
export default{
    data() {
        return {
            restaurants: [
                {
                    name: "Subway",
                    tags:["Salate","Sandwiches"],
                    time: "30-45",
                    minOrder: "20€",
                    deliveryCost: "Free"
                },
                {
                    name: "Dominos",
                    tags:["Pizza","Burger","Desserts"],
                    time: "20-35",
                    minOrder: "10€",
                    deliveryCost: "9,99"
                },
                {
                    name: "India 3",
                    tags:["Curry","Mango"],
                    time: "30-45",
                    minOrder: "25€",
                    deliveryCost: "10"
                },
               
            ]
        };
    },
    components: { RestaurantItem }
}
</script>