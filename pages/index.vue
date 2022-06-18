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

<style>

:root{
  --orange: #FB6100;
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}
</style>
