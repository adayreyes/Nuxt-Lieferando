<template>
    <main>
        <MainHeader/>
        <ProductsList/>
    </main>
</template>

<script>
import MainHeader from "../components/MainHeader.vue";
import ProductsList from "../components/ProductsList.vue";

export default{
    components: { MainHeader, ProductsList }
}

</script>

<style scoped>

main{
    display: flex;
    align-items: center;
    flex-direction: column;
    height: 100vh;
    gap: 1rem;
}


</style>