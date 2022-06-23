<template>
<div class="basket-container">
    <h4>Basket</h4>
    <div class="basket-content">
        <span v-for="item in basketItems" :key="item.name"> {{item.name}}</span>
        
    </div>
</div>
</template>
<script>
export default{
    props:["basketItems"]
}
</script>

<style scoped>
h4{
    border-bottom: 1px solid black;
    width: 100%;
    text-align: center;
    padding: .5rem;
}
.basket-container{
    position: absolute;
    top: -1rem;
    right: 0;
    border-left: 1px solid black;
    height: 100%;
    gap: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 200px;
}
.basket-content{
    display: flex;
    flex-direction: column;
    align-items: center;
}

</style>