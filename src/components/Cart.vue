<template>
    <ul class="list-group" v-for="(product,index) in cart" :key="product.id">
        <li class="list-group-item d-flex justify-content-between align-items-start">
            <div class="ms-2 me-auto">
                <div class="fw-bold">{{product.title}}</div>
                    ${{product.price}}.00
            </div>
                <a @click="deleteProduct(index)" class="badge bg-primary rounded-pill">Eliminar</a>
        </li>
    </ul>
    <h4 class="cart-total">Total: <span class="cart-total-highlight">${{sumTotal()}}.00</span> </h4>
</template>

<script>
export default {
    props:{
        cart:Array,
        deleteProduct:Function
    },
    data(){
        return{
            total: Number
        }
    },
    methods:{
        sumTotal(){
            var sum = this.cart.reduce((sum, value) => (typeof value.price == "number" ? sum + value.price : sum), 0);
            return sum;
        },
        
    }
}
</script>

<style scoped>
.list-group-item{
    margin: 5px 0px 5px 0px;
}
</style>

<style>
.badge{
    cursor: pointer;
    text-decoration: none;
}
.badge:hover{
    color: white;
}
.cart-total{
    color: var(--primary);
}
.cart-total-highlight{
    font-weight: bold;
}
</style>