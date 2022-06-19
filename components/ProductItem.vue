<template>
    <div @click="$emit('showDialog',productInfo)" class="product-item-container">
        <span class="add-icon">+</span>
        <div class="item-header">
            <h2>{{productInfo.name}}</h2>
            <span class="small blue">Product info</span>
        </div>
        <p>{{productInfo.description}}</p>
        <div class="choices">
            Choice of:
            <span v-for="(choices,option) in productInfo.choiceOf" :key="option">{{option}}</span>
        </div>
        <span class="price">{{productInfo.price}}€</span>

    </div>
</template>
<script>
export default {
    props:["productInfo"],
    emits:["showDialog"]
}
</script>
<style scoped>
    .item-header{
        display: flex;
        align-items: center;
        gap: .5rem;
    }

    .add-icon{
        font-weight: bold;
        color: var(--blue);
        font-size: 2rem;
        position: absolute;
        top: 0;
        right: 0;
        border: 1px solid black;
        border-right: none;
        border-top: none;
        padding: 0 .5rem;
    }

    

    .product-item-container{
        border: 1px solid black;
        border-radius: 2px;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        gap: .5rem;
        cursor: pointer;
        transition: all 100ms ease;
        position: relative;
        width: 600px;
       
    
    }

    .product-item-container:hover{
        background-color: #eee;
    }
    .choices{
        font-size: .9rem;
       
        font-style: italic;
    }
    .choices span{
        margin-right: .3rem;
    }

    .choices span::after{
        content: ",";
    }
    .choices span:last-child::after{
        content: ".";
    }

    .price{
        color: var(--orange);
        font-size: 1.2rem;
        font-weight: bold;
    }
</style>