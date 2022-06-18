<template>
<div class="restaurant-item-container">
    <h2>{{ restaurantInfo.name }}</h2>
    <div  class="tags">
        <span v-for="tag,index in restaurantInfo.tags" :key="index">{{ tag }}</span>
    </div>
    <div class="infos-container">
        <div class="info-box">
            <img src="/img/time-8-64.ico" alt="">
            {{ restaurantInfo.time }}
        </div>
        <div class="info-box">
            <img src="/img/bike-4-64.ico" alt="">
            {{ restaurantInfo.deliveryCost }}
        </div>
        <div class="info-box">
            <img src="/img/cart-16-64.ico" alt="">
            {{ restaurantInfo.minOrder }}
        </div>
    </div>
</div>
</template>

<script>
    export default{
    data() {
        return {
            
        }
    },
    props:["restaurantInfo"]
    }
</script>

<style scoped>
    .restaurant-item-container{
        width: 500px;
        border: 1px solid black;
        border-radius: 2px;
        display: flex;
        flex-direction: column;
        margin-bottom: 1rem;
        padding: .5rem;
        cursor: pointer;
        transition: all 100ms ease;
    }

    .restaurant-item-container:hover{
        background-color: #eee;
    }
    .tags{
        display: flex;
        gap: .5rem;
        color: rgb(134, 134, 134);
    }
    .infos-container{
        display: flex;
        gap: 1rem;
        color: rgb(134, 134, 134);
    }

    .info-box{
        display: flex;
        align-items: center;
        gap: .2rem;
    }

    img{
        width: 30px;
    }
</style>