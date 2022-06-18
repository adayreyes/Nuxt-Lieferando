<template>
<main>
  <MainHeader/>
  <RestaurantsList/>
</main>
</template>

<script>
import RestaurantsList from '../components/RestaurantsList.vue';
import MainHeader from '../components/MainHeader.vue'
export default {
    name: "IndexPage",
    components: { RestaurantsList, MainHeader }
}
</script>

<style scoped>


main{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}
</style>
