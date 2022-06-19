<template>
    <div class="main-container">
        <header>
            <div class="title-container">
                <h3>{{ productInfo.name }}</h3>
                <span class="small blue">Product info</span>
            </div>
            <span @click="$emit('closeDialog')" class="close-icon">x</span>
        </header>
        <div class="choice-info-container">
            <span>{{ productInfo.price }}€</span>
            <span>{{ productInfo.description }}</span>
        </div>
        <div class="select-container">
            <div v-for="choices, option in productInfo.choiceOf" :key="option">
                <span>Select your {{ option }}</span>
                <select :name="option" :id="option">
                    <option v-for="choice in choices" :key="choice" :value="choice">{{ choice }}</option>
                </select>
            </div>
        </div>
        <footer>
            <div class="counter-container">
                <span @click="reduceQuantity">-</span>
                <span class="quantity">{{ quantity }}</span>
                <span @click="increaseQuantity">+</span>
            </div>
            <span class="price">{{ total }}€</span>
        </footer>
    </div>
</template>
<script>
export default {
    data() {
        return {
            quantity: 1,
            total: this.productInfo.price
        }
    },
    props: ["productInfo"],
    methods: {
        reduceQuantity() {
            if (this.quantity > 1) {
                this.quantity--
                this.total = (this.productInfo.price * this.quantity).toFixed(2)
            }
        },
        increaseQuantity() {
            if (this.quantity < 30) {
                this.quantity++
                this.total = (this.productInfo.price * this.quantity).toFixed(2)

            }
        }
    },
    emits: ["closeDialog"]
}

</script>

<style scoped>
.main-container {
    border: 1px solid black;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 600px;
    height: 400px;
    position: absolute;
    top: 20%;
    left: 32%;
    z-index: 999;
    background-color: white;
}

.select-container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.select-container div {
    display: flex;
    flex-direction: column;
}

select {
    width: 300px;
    font-size: 1.2rem;
}

.close-icon {
    font-size: 1.5rem;
    font-weight: bold;
    position: absolute;
    top: -.8rem;
    right: 0;
    cursor: pointer;
}

header {
    display: flex;
    position: relative;

}

.title-container {
    display: flex;
    align-items: baseline;
    gap: .5rem;
}

.choice-info-container {
    display: flex;
    flex-direction: column;
}

footer {
    display: flex;
    justify-content: space-between;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 1rem;

}

.counter-container {
    display: flex;

}

.counter-container span {
    border: 1px solid black;

}

.counter-container .quantity {
    padding: .4rem .7rem;
    border-left: none;
    border-right: none;
}

.counter-container span:first-child,
.counter-container span:last-child {
    padding: .3rem .6rem;
    cursor: pointer;

}

.price {
    color: var(--orange);
    font-weight: bold;
    font-size: 1.2rem;
}
</style>