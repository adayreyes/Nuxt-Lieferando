<template>
    <div class="main-container">
        <header>
            <div class="title-container">
                <h3>Schirippen Open-Sandwich (6 pieces)</h3>
                <span class="small blue">Product info</span>
            </div>
            <span @click="$emit('closeDialog')" class="close-icon">x</span>
        </header>
        <div class="choice-info-container">
            <span>10,00€</span>
            <span>with two topping of choice</span>
        </div>
        <div class="select-container">
            <div>
                <span>Your 1. topping:</span>
                <select name="topping-1" id="topping-1">
                    <option value="chicken">chicken</option>
                    <option value="mett">mett</option>
                    <option value="cheese">cheese</option>
                </select>
            </div>
            <div>
                <span>Your 2. topping:</span>
                <select name="topping-2" id="topping-2">
                    <option value="chicken">chicken</option>
                    <option value="mett">mett</option>
                    <option value="cheese">cheese</option>
                </select>
            </div>
        </div>
        <footer>
            <div class="counter-container">
                <span @click="reduceQuantity">-</span>
                <span class="quantity">{{quantity}}</span>
                <span @click="increaseQuantity">+</span>
            </div>
            <span class="price">10,00€</span>
        </footer>
    </div>
</template>
<script>
export default{
   data() {
    return {
        quantity: 1,
    }
   },
   methods: {
    reduceQuantity(){
        if(this.quantity != 1){
            this.quantity--
        }
    },
    increaseQuantity(){
        if(this.quantity < 30){
            this.quantity++
        }
    }
   },
   emits:["closeDialog"]
}

</script>

<style scoped>

.main-container{
    border: 1px solid black;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 600px;
    height: 600px;
    position: absolute;
    top: 20%;
    left: 32%;
    z-index: 999;
    background-color: white;
}

.close-icon{
    font-size: 1.5rem;
    font-weight: bold;
    position: absolute;
    top: -.8rem;
    right: 0;
    cursor: pointer;
}

header{
    display: flex;
    position: relative;
    
}
.title-container{
    display: flex;
    align-items: baseline;
    gap: .5rem;
}
.choice-info-container{
    display: flex;
    flex-direction: column;
}

footer{
    display: flex;
    justify-content: space-between;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 1rem;
    
}
.counter-container{
    display: flex;
    
}
.counter-container span{
    border: 1px solid black;
    
}
.counter-container .quantity{
    padding: .4rem .7rem;
    border-left: none;
    border-right: none;
}
.counter-container span:first-child, .counter-container span:last-child{
    padding: .3rem .6rem;
    cursor: pointer;
    
}

.price{
    color: var(--orange);
    font-weight: bold;
    font-size: 1.2rem;
}
</style>